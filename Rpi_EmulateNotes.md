# Raspberry pi 4 Emulate with qemu

## Info
 - This tutorial is for emulate raspberry pi4 with Qemu. it going to use Linux kernel from downloaded iso, not going to compile. 

### Libraries

 -  Download qemu aarch64 library
```
 pacman -S qemu-system-aarch64
```

### Setting Up Environment
```
mkdir ./emulate
cd ./emulate
```


### Download ISO

 - 64 bit, lite version.
```
	wget https://downloads.raspberrypi.org/raspios_lite_arm64/images/raspios_lite_arm64-2023-05-03/2023-05-03-raspios-bullseye-arm64-lite.img.xz
```

### Extract and Rename ISO.

```
	unxz 2023-05-03-raspios-bullseye-arm64-lite.img.xz
```
```
	mv 2023-05-03-raspios-bullseye-arm64-lite.img rpi.img
```

### Mount ISO
 ```
	losetup -P /dev/loop0 rpi.img
	mkdir /mnt/raspbian
	mount /dev/loop0p2 /mnt/raspbian
	mount /dev/loop0p1 /mnt/raspbian/boot
```
### Copy Compiled Kernel and Device Tree
```
	cp /mnt/raspbian/boot/kernel8.img kernel8.img
	cp /mnt/raspbian/boot/bcm2710-rpi-3-b.dtb bcm2710-rpi-3-b.dtb

```

### Resize ISO
```
	qemu-img resize rpi.img 4G
```

### Run Qemu
- Now we have all Qemu needs to emulate raspberry pi 4.
```

	qemu-system-aarch64 -machine raspi3b -cpu cortex-a72 -dtb bcm2710-rpi-3-b.dtb -m 1G -smp 4 -kernel kernel8.img -sd rpi.img -append "rw earlyprintk loglevel=8 console=ttyAMA0,115200 dwc_otg.lpm_enable=0 root=/dev/mmcblk0p2 rootdelay=1" -device usb-net,netdev=net0 -netdev user,id=net0,hostfwd=tcp::2222-:22 -device usb-kbd 

```