# Buildroot Package for LimePi Zero
Opensource development package for LimePi Zero



### Install necessary packages
``` shell
sudo apt install wget unzip build-essential git bc swig libncurses-dev libpython3-dev libssl-dev
sudo apt install python3-distutils
```

### Download BSP
**Notice: Root permission is not necessery for download or extract.**
```shell
git clone https://github.com/TraxBee/buildroot-lime-pi.git
```

## Make the first build
**Notice: Root permission is not necessery for build firmware.**

### Apply defconfig
**Caution: Apply defconfig will reset all buildroot configurations to default values.**

**Generally, you only need to apply it once.**
```shell
cd buildroot-lime-pi
make traxbee_limepi_r1_defconfig
```

### Regular build
```shell
make
```

## Speed up build progress

### Download speed
Buildroot will download sourcecode when compiling the firmware. You can grab a **TRUSTWORTHY** archive of 'dl' folder for speed up.

### Compile speed
If you have a multicore CPU, you can try
```
make -j ${YOUR_CPU_COUNT}
```
or buy a powerful PC for yourself.

## Flashing firmware to target
You can flash a board by Linux (Recommended) or Windows system.
### [Here is the manual.](flashutils/README.md)

## Helper Scripts
- rebuild-uboot.sh: Recompile U-Boot when you direct edit U-Boot sourcecode.
- rebuild-kernel.sh: Recompile Kernel when you direct edit Kernel sourcecode.
- emulate-chroot.sh: Emulate target rootfs by chroot.
