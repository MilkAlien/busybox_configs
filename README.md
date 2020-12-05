# busybox_configs

(ADSL modem/router *****v4)


```
### .config >> busybox-1.*/
sudo apt install gcc-mips-linux-gnu
tar -xjf busybox-1*.tar.bz2
cd busybox-1.*/
make -j4 menuconfig
make -j4
sudo make -j4 install DESTDIR=/PATH/to/squashfs-root/
sudo sh ./clear_addons_other-dir.sh                 // Edit for youre dir '_install'
--------------------------------------------------
You will probably need to make your busybox binary
setuid root to ensure all configured applets will
work properly.
--------------------------------------------------
sudo shmod +s /PATH/to/squashfs-root/bin/busybox    // По желанию!
sudo cp -ar _install/* /PATH/to/squashfs-root/
sudo mksquashfs squashfs-root/ gpon.squashfs -comp lzma -b 131072 -nopad
```
