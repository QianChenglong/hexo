---
title: VirtualBox共享文件夹配置
categories: [arch]
tags: [arch, virtualbox]
date: 2015-06-24 19:02:47
---

# 环境

-   ArchLinux

# 步骤

1.  安装模块

        pacman -S virtualbox-guest-modules

1.  手动载入模块

        modprobe -a vboxsf

    若提示`Module not found`，则执行：

        depmod $(uname -r)

1.  开机自动载入模块

        echo vboxsf >/etc/modules-load.d/virtualbox.conf

1.  创建挂载点

        mkdir /data

1.  在虚拟机控制中，加入共享文件夹

        E_DRIVE

1.  挂载

    -   手动挂载

            mount -t vboxsf E_DRIVE /data

    -   自动挂载

            /etc/fstab

            E_DRIVE /data vboxsf

# 常见问题

-   挂载失败

    错误提示：

        [cpp] view plaincopy
        mount: wrong fs type, bad option, bad superblock on E_DRIVE,
               missing codepage or helper program, or other error
               (for several filesystems (e.g. nfs, cifs) you might
               need a /sbin/mount.<type> helper program)
               In some cases useful info is found in syslog - try
               dmesg | tail or so

    解决过程：

    1.   dmesg | tail

            sf_read_super_aux err=-22

    1.  查看vboxsf链接

            vincent@vincent-VirtualBox:/mnt$ ls -al /sbin/mount.vboxsf
            lrwxrwxrwx 1 root root 40 Jun 19 09:38 /sbin/mount.vboxsf -> /usr/lib/VBoxGuestAdditions/mount.vboxsf

    1.  发现链接不对，重新链接

            ln -s /opt/VBoxGuestAdditions-4.3.10/lib/VBoxGuestAdditions/mount.vboxsf /sbin/mount.vboxsf

# 参考

1.  <https://wiki.archlinux.org/index.php/VirtualBox#Installation_steps_for_Arch_Linux_guests>
