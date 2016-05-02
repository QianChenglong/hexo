---
title: tomcat部署war包
categories: [tomcat]
tags: [tomcat, war]
date: 2015-06-18 15:13:19
---

# 环境

-   ubuntu-14.04

-   tomcat7

# 步骤

1.  复制war包到`/var/lib/tomcat/webapps`

1.  修改配置文件

        <Host name="localhost"  appBase="webapps"
                    unpackWARs="true" autoDeploy="true">
                +++ <Context docBase="/var/lib/tomcat7/webapps/chaojizhun.war" path="/chaojizhun" reloadable="true"/>
        </Host>

1.  重启tomcat

        /etc/init.d/tomcat7 restart
