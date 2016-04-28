# kernel-postinst-d
Scripts for kernel post-installation routines

Intended to be placed into ``/etc/kernel/postinst.d`` directory. Will be automatically executed on ``make install`` of linux kernel.

- __90-mount-boot__ and __95-umount-boot__ are used to mount and unmount ``/boot`` partition according to ``/etc/fstab``
- __91-modules-install__ automatically issue ``make modules_install``
- __92-dracut__ generate new initramfs using [dracut](https://dracut.wiki.kernel.org).
- __93-bootctl-entry__ creates "/boot/loader/entries/<version>.conf" file for [systemd bootloader](https://www.freedesktop.org/wiki/Specifications/BootLoaderSpec/)
- __94-bootctl-default__ replaces or creates _default_ section inside /boot/loader/loader.conf
