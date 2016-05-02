-   apt-get intall rsync

-   vi /etc/rsyncd.conf

```
#motd file = /etc/rsyncd.motd
log file = /var/log/rsyncd.log
pid file = /var/run/rsyncd.pid
lock file = /var/run/rsync.lock

[server]
   path = /home/wallace/server
   comment = gupiaoxianji server code
   uid = wallace
   gid = wallace
   read only = no
   list = yes
   #hosts allow = 10.0.0.1/0
   auth users = wallace
   secrets file = /etc/rsyncd.scrt
   strict modes = false
```

-   vi /etc/rsyncd.scrt

        wallace:wallacework

-   vi /etc/default/rsync

        RSYNC_ENABLE=true

-   /etc/init.d/rsync restart


# 参考

1.  <http://ubuntuforums.org/showthread.php?t=1252720>
