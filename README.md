# busybox_configs

to *****v4


```
sudo apt install gcc-mips-linux-gnu
tar -xjf busybox-1.26.2.tar.bz2
cd busybox-1.26.2/
make -j4 menuconfig
make -j4
sudo make install DESTDIR=/PATH/to/squashfs-root/
sudo mksquashfs squashfs-root/ gpon.squashfs -comp lzma -b 131072 -nopad
```
