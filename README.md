# busybox_configs

(ADSL modem/router *****v4)


```
### .config >> busybox-1.32.0/
sudo apt install gcc-mips-linux-gnu
tar -xjf busybox-1.32.0.tar.bz2
cd busybox-1.32.0/
make -j4 menuconfig
make -j4
sudo make -j4 install                               // Добавить префикс 'DESTDIR=/PATH/to/squashfs-root/', если линки не получились.
--------------------------------------------------
You will probably need to make your busybox binary
setuid root to ensure all configured applets will
work properly.
--------------------------------------------------
sudo cp -r _install/* /PATH/to/squashfs-root/
sudo shmod +s /PATH/to/squashfs-root/bin/busybox    // По желанию!
sudo mksquashfs squashfs-root/ gpon.squashfs -comp lzma -b 131072 -nopad
```
