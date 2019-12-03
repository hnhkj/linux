# README_nano-5.2-flash

## nano-5.2-flash

reference document <https://whycan.cn/t_3087.html>

```sh
git clone https://github.com/Lichee-Pi/linux.git -b nano-5.2-flash
#git cloen https://github.com/hnhkj/linux.git -b nano-5.2-flash
cp config.whycan .config
make ARCH=arm menuconfig
> Device Drivers > Network device support > Wireless LAN [*] Realtek devices
                                                         <*> Realtek rtlwifi family of devices
                                                         <*> RTL8723AU/RTL8188[CR]U/RTL819[12]CU (mac80211) support
make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- -j4 &&
sunxi-fel -p spiflash-write 0x110000 arch/arm/boot/zImage &&
sunxi-fel -p spiflash-write 0x100000 arch/arm/boot/dts/suniv-f1c100s-licheepi-nano.dtb
```

## log

***don't running. need to check***

```sh
U-Boot SPL 2018.01-05689-g32d01b6cde-dirty (Nov 27 2019 - 16:11:45)
DRAM: 64 MiB
Trying to boot from sunxi SPI


U-Boot 2018.01-05689-g32d01b6cde-dirty (Nov 27 2019 - 16:11:45 +0800) Allwinner Technology

CPU:   Allwinner F Series (SUNIV)
Model: Lichee Pi Nano
DRAM:  64 MiB
MMC:   SUNXI SD/MMC: 0
SF: Detected w25q128bv with page size 256 Bytes, erase size 4 KiB, total 16 MiB
*** Warning - bad CRC, using default environment

In:    serial@1c25000
Out:   serial@1c25000
Err:   serial@1c25000
Net:   No ethernet found.
starting USB...
No controllers found
Hit any key to stop autoboot:  0
SF: Detected w25q128bv with page size 256 Bytes, erase size 4 KiB, total 16 MiB
device 0 offset 0x100000, size 0x4000
SF: 16384 bytes @ 0x100000 Read: OK
device 0 offset 0x110000, size 0x400000
SF: 4194304 bytes @ 0x110000 Read: OK
## Flattened Device Tree blob at 80c00000
   Booting using the fdt blob at 0x80c00000
   Loading Device Tree to 816fa000, end 816ff051 ... OK

Starting kernel ...

[    0.000000] Booting Linux on physical CPU 0x0
[    0.000000] Linux version 5.2.0-licheepi-nano+ (ubuntu@ubuntu-B150M-VP) (gcc version 7.4.0 (Ubuntu/Linaro 7.4.0-1ubuntu1~18.04.1)) #43 Tue Dec 3 14:58:54 CST 2019
[    0.000000] CPU: ARM926EJ-S [41069265] revision 5 (ARMv5TEJ), cr=0005317f
[    0.000000] CPU: VIVT data cache, VIVT instruction cache
[    0.000000] OF: fdt: Machine model: Lichee Pi Nano
[    0.000000] Memory policy: Data cache writeback
[    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 16256
[    0.000000] Kernel command line: console=ttyS0,115200 panic=5 rootwait root=/dev/mtdblock3 rw rootfstype=jffs2
[    0.000000] Dentry cache hash table entries: 8192 (order: 3, 32768 bytes)
[    0.000000] Inode-cache hash table entries: 4096 (order: 2, 16384 bytes)
[    0.000000] Memory: 55140K/65536K available (6144K kernel code, 278K rwdata, 1516K rodata, 1024K init, 228K bss, 10396K reserved, 0K cma-reserved, 0K highmem)
[    0.000000] SLUB: HWalign=32, Order=0-3, MinObjects=0, CPUs=1, Nodes=1
[    0.000000] NR_IRQS: 16, nr_irqs: 16, preallocated irqs: 16
[    0.000000] random: get_random_bytes called from start_kernel+0x254/0x42c with crng_init=0
[    0.000045] sched_clock: 32 bits at 24MHz, resolution 41ns, wraps every 89478484971ns
[    0.000122] clocksource: timer: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 79635851949 ns
[    0.000653] Console: colour dummy device 80x30
[    0.000744] Calibrating delay loop... 203.16 BogoMIPS (lpj=1015808)
[    0.070241] pid_max: default: 32768 minimum: 301
[    0.070656] Mount-cache hash table entries: 1024 (order: 0, 4096 bytes)
[    0.070700] Mountpoint-cache hash table entries: 1024 (order: 0, 4096 bytes)
[    0.072299] CPU: Testing write buffer coherency: ok
[    0.074135] Setting up static identity map for 0x80100000 - 0x80100058
[    0.076324] devtmpfs: initialized
[    0.083177] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 19112604462750000 ns
[    0.083241] futex hash table entries: 256 (order: -1, 3072 bytes)
[    0.083527] pinctrl core: initialized pinctrl subsystem
[    0.085493] NET: Registered protocol family 16
[    0.086904] DMA: preallocated 256 KiB pool for atomic coherent allocations
[    0.088913] cpuidle: using governor menu
[    0.138544] SCSI subsystem initialized
[    0.138924] usbcore: registered new interface driver usbfs
[    0.139077] usbcore: registered new interface driver hub
[    0.139252] usbcore: registered new device driver usb
[    0.139702] pps_core: LinuxPPS API ver. 1 registered
[    0.139727] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
[    0.140386] Advanced Linux Sound Architecture Driver Initialized.
[    0.142064] clocksource: Switched to clocksource timer
[    0.169968] NET: Registered protocol family 2
[    0.171484] tcp_listen_portaddr_hash hash table entries: 512 (order: 0, 4096 bytes)
[    0.171562] TCP established hash table entries: 1024 (order: 0, 4096 bytes)
[    0.171627] TCP bind hash table entries: 1024 (order: 0, 4096 bytes)
[    0.171674] TCP: Hash tables configured (established 1024 bind 1024)
[    0.171945] UDP hash table entries: 256 (order: 0, 4096 bytes)
[    0.172004] UDP-Lite hash table entries: 256 (order: 0, 4096 bytes)
[    0.172644] NET: Registered protocol family 1
[    0.175176] NetWinder Floating Point Emulator V0.97 (double precision)
[    0.177190] Initialise system trusted keyrings
[    0.177741] workingset: timestamp_bits=30 max_order=14 bucket_order=0
[    0.204491] Key type asymmetric registered
[    0.204532] Asymmetric key parser 'x509' registered
[    0.204705] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 252)
[    0.204731] io scheduler mq-deadline registered
[    0.204748] io scheduler kyber registered
[    0.206863] sun4i-usb-phy 1c13400.phy: Couldn't request ID GPIO
[    0.217102] suniv-f1c100s-pinctrl 1c20800.pinctrl: initialized sunXi PIO driver
[    0.390081] Serial: 8250/16550 driver, 8 ports, IRQ sharing disabled
[    0.395737] suniv-f1c100s-pinctrl 1c20800.pinctrl: 1c20800.pinctrl supply vcc-pe not found, using dummy regulator
[    0.397434] printk: console [ttyS0] disabled
[    0.417682] 1c25000.serial: ttyS0 at MMIO 0x1c25000 (irq = 24, base_baud = 6250000) is a 16550A
[    0.797569] printk: console [ttyS0] enabled
[    0.805888] suniv-f1c100s-pinctrl 1c20800.pinctrl: 1c20800.pinctrl supply vcc-pd not found, using dummy regulator
[    0.824668] SCSI Media Changer driver v0.25
[    0.830264] suniv-f1c100s-pinctrl 1c20800.pinctrl: 1c20800.pinctrl supply vcc-pc not found, using dummy regulator
[    0.843280] m25p80 spi0.0: w25q128 (16384 Kbytes)
[    0.848868] 4 fixed-partitions partitions found on MTD device spi0.0
[    0.855348] Creating 4 MTD partitions on "spi0.0":
[    0.860159] 0x000000000000-0x000000100000 : "u-boot"
[    0.866660] 0x000000100000-0x000000110000 : "dtb"
[    0.872803] 0x000000110000-0x000000510000 : "kernel"
[    0.879073] 0x000000510000-0x000001000000 : "rootfs"
[    0.885988] PPP generic driver version 2.4.2
[    0.891024] usbcore: registered new interface driver rtl8192cu
[    0.897141] usbcore: registered new interface driver rtl8xxxu
[    0.902963] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
[    0.909480] ehci-platform: EHCI generic platform driver
[    0.915051] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
[    0.921275] ohci-platform: OHCI generic platform driver
[    0.926989] usbcore: registered new interface driver usb-storage
[    0.934120] udc-core: couldn't find an available UDC - added [g_cdc] to list of pending drivers
[    0.943246] i2c /dev entries driver
[    0.950590] suniv-f1c100s-pinctrl 1c20800.pinctrl: 1c20800.pinctrl supply vcc-pf not found, using dummy regulator
[    0.988610] sunxi-mmc 1c0f000.mmc: initialized, max. request size: 16384 KB
[    0.997897] usbcore: registered new interface driver usbhid
[    1.003596] usbhid: USB HID core driver
[    1.023738] NET: Registered protocol family 17
[    1.028292] Key type dns_resolver registered
[    1.034906] Loading compiled-in X.509 certificates
[    1.050794] suniv-f1c100s-pinctrl 1c20800.pinctrl: 1c20800.pinctrl supply vcc-pd not found, using dummy regulator
[    1.062293] sun4i-backend 1e60000.display-backend: Couldn't find matching frontend, frontend features disabled
[    1.073102] sun4i-drm display-engine: bound 1e60000.display-backend (ops 0xc0737d74)
[    1.082056] sun4i-drm display-engine: bound 1c0c000.lcd-controller (ops 0xc07369cc)
[    1.089844] [drm] Supports vblank timestamp caching Rev 2 (21.10.2013).
[    1.096495] [drm] No driver support for vblank timestamp query.
[    1.104187] [drm] Initialized sun4i-drm 1.0.0 20150629 for display-engine on minor 0
[    1.359391] Console: switching to colour frame buffer device 100x30
[    1.399195] sun4i-drm display-engine: fb0: sun4i-drmdrmfb frame buffer device
[    1.408100] usb_phy_generic usb_phy_generic.0.auto: usb_phy_generic.0.auto supply vcc not found, using dummy regulator
[    1.420184] musb-hdrc musb-hdrc.1.auto: MUSB HDRC host driver
[    1.426224] musb-hdrc musb-hdrc.1.auto: new USB bus registered, assigned bus number 1
[    1.436648] hub 1-0:1.0: USB hub found
[    1.440655] hub 1-0:1.0: 1 port detected
[    1.446501] using random self ethernet address
[    1.450968] using random host ethernet address
[    1.457565] usb0: HOST MAC 92:af:70:cf:28:f9
[    1.461989] usb0: MAC ae:6a:80:a4:bb:19
[    1.466096] g_cdc gadget: CDC Composite Gadget, version: King Kamehameha Day 2008
[    1.473708] g_cdc gadget: g_cdc ready
[    1.478584] cfg80211: Loading compiled-in X.509 certificates for regulatory database
[    1.496803] cfg80211: Loaded X.509 cert 'sforshee: 00b28ddf47aef9cea7'
[    1.503667] ALSA device list:
[    1.506720]   #0: Loopback 1
[    1.510612] platform regulatory.0: Direct firmware load for regulatory.db failed with error -2
[    1.519357] cfg80211: failed to load regulatory.db
[    1.525030] Waiting for root device /dev/mtdblock3...
[    2.138881] random: fast init done
[    2.955304] g_cdc gadget: high-speed config #1: CDC Composite (ECM + ACM)

don't continue... need to check.
```