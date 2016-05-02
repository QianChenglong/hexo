---
title: ubuntu-使用pptpd搭建vpn
tags: [ubuntu, vpn]
date: 2015-10-30 15:19:49
---

# 步骤

1.  安装`pptpd`

        apt-get install pptpd

1.  `vi /etc/pptpd.conf`

        option /etc/ppp/pptpd-option                    #指定PPP选项文件的位置
        debug                                           #启用调试模式
        localip 192.168.0.1                             #VPN服务器的虚拟ip
        remoteip 192.168.0.200-238,192.168.0.245        #分配给VPN客户端的虚拟ip

1.  `vi /etc/ppp/pptpd-options`

        name pptpd                      #pptpd服务的名称
        refuse-pap                      #拒绝pap身份认证模式
        refuse-chap                     #拒绝chap身份认证模式
        refuse-mschap                   #拒绝mschap身份认证模式
        require-mschap-v2               #允许mschap-v2身份认证模式
        require-mppe-128                #允许mppe 128位加密身份认证模式
        ms-dns 8.8.8.8                  #使用Google DNS
        ms-dns 8.8.4.4                  #使用Google DNS
        proxyarp                        #arp代理
        debug                           #调试模式
        dump                            #服务启动时打印出所有配置信息
        lock                            #锁定TTY设备
        nobsdcomp                       #禁用BSD压缩模式

1.  添加用户`vi /etc/ppp/chap-secrets`

        #格式：用户名   服务类型   密码   分配的ip地址
        test    *    1234    *

1.  重启PPTPD服务

        service pptpd restart

1.  配置网络和路由规则,设置ipv4转发

        sed -i 's/#net.ipv4.ip_forward=1/net.ipv4.ip_forward=1/g' /etc/sysctl.conf
        sysctl -p

        iptables -t nat -A POSTROUTING -s 192.168.0.0/24 -o eth0 -j MASQUERADE

1.  设置MTU来确保过大的包不会被丢弃(可选)

        iptables -I FORWARD -s 192.168.0.0/24 -p tcp --syn -i ppp+ -j TCPMSS --set-mss 1300

1.  备份iptables

        iptables-save > /etc/iptables.rule

1.  开机自动加载

        vi /etc/network/interfaces

        pre-up iptables-restore < /etc/iptables.rule

# 参考

1.  <http://blog.fens.me/ubuntu-vpn-pptp/>
1.  <http://blueve.me/archives/1087>
1.  <http://www.777s.me/centos-pptp.html>
