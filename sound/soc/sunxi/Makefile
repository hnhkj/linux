# SPDX-License-Identifier: GPL-2.0
obj-$(CONFIG_SND_SUN4I_CODEC) += sun4i-codec.o
obj-$(CONFIG_SND_SUN4I_I2S) += sun4i-i2s.o
obj-$(CONFIG_SND_SUN4I_SPDIF) += sun4i-spdif.o
obj-$(CONFIG_SND_SUN8I_CODEC_ANALOG) += sun8i-codec-analog.o
obj-$(CONFIG_SND_SUN8I_CODEC) += sun8i-codec.o

ifneq ($(CONFIG_SND_SOC_SUNXI_RW),)
#snd-sunxi-soc-objs += sunxi_rw_func.o
obj-y += sunxi_rw_func.o
endif

#sunivw1p1
obj-$(CONFIG_SND_SOC_INTERNAL_SUNIVW1P1_AUDIOCODEC) += sunivw1p1_codec.o
obj-$(CONFIG_SND_SOC_SUNIVW1P1_CODEC_CPU_DAI) += sunivw1p1_cpudai.o
obj-$(CONFIG_SND_SOC_SUNIVW1P1_CPU_DAUDIO) += sunivw1p1_daudio.o

#sunivw1p1
obj-$(CONFIG_SND_SOC_SUNIVW1P1_AUDIO_CODEC_MACHINE) += sunivw1p1_sndcodec.o