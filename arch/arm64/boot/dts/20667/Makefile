ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)
	dtbo-$(CONFIG_ARCH_TRINKET) += trinket-idp-overlay-20667.dtbo
	trinket-idp-overlay-20667.dtbo-base := trinket-20667.dtb
	
else
	dtb-$(CONFIG_ARCH_TRINKET)	+= trinket-idp-20667.dtb
endif
always		:= $(dtb-y)
subdir-y	:= $(dts-dirs)
clean-files	:= *.dtb *.dtbo
