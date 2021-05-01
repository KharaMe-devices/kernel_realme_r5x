# SPDX-License-Identifier: GPL-2.0
# ifndef VENDOR_EDIT
# Weizhi.Chen@BSP.Kernel.Driver, 2019/10/09, Modify for use oppo target dts for kernel.
#dts-dirs += actions
#dts-dirs += al
#dts-dirs += allwinner
#dts-dirs += altera
#dts-dirs += amd
#dts-dirs += amlogic
#dts-dirs += apm
#dts-dirs += arm
#dts-dirs += broadcom
#dts-dirs += cavium
#dts-dirs += exynos
#dts-dirs += freescale
#dts-dirs += hisilicon
#dts-dirs += marvell
#dts-dirs += mediatek
#dts-dirs += nvidia
#dts-dirs += qcom
#dts-dirs += realtek
#dts-dirs += renesas
#dts-dirs += rockchip
#dts-dirs += socionext
#dts-dirs += sprd
#dts-dirs += xilinx
#dts-dirs += lg
#dts-dirs += zte
# else
#dts-dirs += 19375
# endif /* VENDOR_EDIT */
#ifdef VENDOR_EDIT
#qiantao @bsp.kernel.drvier ,2019/12/6 ,Modify for user oppo targer dts for kernel
#dts-dirs += 19571
# endif /* VENDOR_EDIT */
#ifdef VENDOR_EDIT
#//zhye@BSP.Boot.Bootflow, 2019-2-19, add for 6125P upgrade
#dts-dirs += 19021
dts-dirs += 19631
dts-dirs += 20667
#endif

subdir-y	:= $(dts-dirs)

dtstree		:= $(srctree)/$(src)

dtb-$(CONFIG_OF_ALL_DTBS) := $(patsubst $(dtstree)/%.dts,%.dtb, $(foreach d,$(dts-dirs), $(wildcard $(dtstree)/$(d)/*.dts)))

always		:= $(dtb-y)

targets += dtbs

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif
targets += $(DTB_LIST)

dtbs: $(addprefix $(obj)/, $(DTB_LIST))

clean-files := dts/*.dtb *.dtb
