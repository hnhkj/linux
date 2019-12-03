# README

## branch/nano_ethMOH

```sh
#git clone https://github.com/Lichee-Pi/linux.git --depth=1 -b nano-4.14-exp
git clone https://github.com/hnhkj/linux -b nano_ethMOH
cd linux
wget http://nano.lichee.pro/_static/step_by_step/lichee_nano_linux.config
cp lichee_nano_linux.config .config
make ARCH=arm menuconfig

```

#### 声音

求助F1c100s声卡问题 <https://whycan.cn/t_3085.html>

```sh
 > Device Drivers > Sound card support > Advanced Linux Sound Architecture > ALSA for SoC audio support > Allwinner SoC Audio support [*] Allwinner f1c500s codec support
```