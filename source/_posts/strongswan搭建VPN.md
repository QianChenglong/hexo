---
title: strongswan搭建VPN
categories: [VPN]
tags: [VPN, vps, IKEV2, strongswan]
date: 2015-03-04 14:22:58
---

# 环境

-   VPS服务商：digitalocean

-   VPS系统：ubuntu-14.04-64

-   VPN：strongSwan-5.1.2

# 准备编译环境

    apt-get install build-essential
    aptitude install libgmp10 libgmp3-dev libssl-dev pkg-config libpcsclite-dev libpam0g-dev

# 编译安装

-   下载源码

        wget http://download.strongswan.org/strongswan-5.1.2.tar.bz2

-   解压

        tar -jxvf strongswan-5.1.2.tar.bz2 & cd strongswan-5.1.2

-   生成Makefile

        ./configure --prefix=/usr --sysconfdir=/etc  --enable-openssl --enable-nat-transport --disable-mysql --disable-ldap  --disable-static --enable-shared --enable-md4 --enable-eap-mschapv2 --enable-eap-aka --enable-eap-aka-3gpp2  --enable-eap-gtc --enable-eap-identity --enable-eap-md5 --enable-eap-peap --enable-eap-radius --enable-eap-sim --enable-eap-sim-file --enable-eap-simaka-pseudonym --enable-eap-simaka-reauth --enable-eap-simaka-sql --enable-eap-tls --enable-eap-tnc --enable-eap-ttls


-   编译安装

        make && make install

# 生成证书

## 根证书

-   生成私钥

        ipsec pki --gen --outform pem > caKey.pem

-   基于这个私钥自己签一个CA证书

        ipsec pki --self --in ca.pem --dn "C=CN, O=strongSwan, CN=107.170.222.166" --ca --outform pem > caCert.pem

## 服务器证书

-   生成私钥

    ipsec pki --gen --outform pem > serverKey.pem

-   基于这个私钥自己签一个CA证书

    ipsec pki --pub --in serverKey.pem | ipsec pki --issue --cacert caCert.pem --cakey caKey.pem --dn "C=CN, O=strongSwan, CN=107.170.222.166" --san="107.170.222.166" --flag serverAuth --flag ikeIntermediate --outform pem > serverCert.pem

    **注：**

        -   VPS的公网IP即自己的VPS的IP

## 客户端证书

-   生成私钥

        ipsec pki --gen --outform pem > clientKey.pem

-   基于这个私钥自己签一个 CA 证书

        ipsec pki --pub --in clientKey.pem | ipsec pki --issue --cacert caCert.pem --cakey caKey.pem --dn "C=CN, O=strongSwan, CN=client" --outform pem > clientCert.pem

-   将该证书转换为`P12`格式

        openssl pkcs12 -export -inkey clientKey.pem -in clientCert.pem -name "client" -certfile caCert.pem -caname "strongSwan CA" -out clientCert.p12

-   使用`winscp`等工具将该证书`clientCert.p12`下载到本地

# 安装证书

    cp caCert.pem /etc/ipsec.d/cacerts/
    cp serverCert.pem /etc/ipsec.d/certs/
    cp serverKey.pem /etc/ipsec.d/private/

# 服务端配置

## /etc/ipsec.conf

```conf
config setup

conn %default
    keyexchange=ikev2
    ike=aes256-sha1-modp1024! 
    esp=aes256-sha1!
    dpdaction=clear
    dpddelay=300s
    rekey=no

conn windows7
    left=%any
    leftauth=pubkey
    leftcert=serverCert.pem
    leftid=@107.170.222.166
    leftsubnet=0.0.0.0/0
    right=%any
    rightauth=eap-mschapv2
    rightsourceip=10.11.1.0/24
    #rightsendcert=never
    eap_identity=%any
```

# /etc/ipsec.secrets

```conf
: RSA serverKey.pem
qian : EAP "test"
```

# /etc/strongswan.conf

```conf
charon {
        dns1 = 8.8.8.8
        load_modular = yes
        plugins {
                include strongswan.d/charon/*.conf
        }
}

include strongswan.d/*.conf
```

# 配置iptables转发

    iptables -A INPUT -p udp --dport 500 -j ACCEPT
    iptables -A INPUT -p udp --dport 4500 -j ACCEPT
    echo 1 > /proc/sys/net/ipv4/ip_forward
    iptables -t nat -A POSTROUTING -s 10.11.1.0/24 -o eth0 -j MASQUERADE  #地址与上面地址池对应
    iptables -A FORWARD -s 10.11.1.0/24 -j ACCEPT     #同上

**Note:**为避免VPS重启后NAT功能失效，可以把如上5行命令添加到 /etc/rc.local 文件中，添加在exit那一行之前即可。

# 重启`strongSwan`

    ipsec restart

**Note:**可以追加`--nofork`选项，帮助调试

# 客户端配置

## win7

### 导入证书到`win7`

参考<https://wiki.strongswan.org/projects/strongswan/wiki/Win7Certs>

### 建立VPN连接

参考<https://wiki.strongswan.org/projects/strongswan/wiki/Win7Config>

# 参考

1.  <https://www.zeitgeist.se/2013/11/22/strongswan-howto-create-your-own-vpn/>
1.  <https://zh.opensuse.org/SDB:Setup_Ipsec_VPN_with_Strongswan>
1.  <http://www.csnc.ch/misc/files/publications/2009_scsII_andreas_steffen_VPNWindows7x.pdf>
1.  <https://gist.github.com/losisli/11081793>
