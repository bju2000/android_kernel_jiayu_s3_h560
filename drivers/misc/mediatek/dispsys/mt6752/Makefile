# drivers/dispsys
include $(srctree)/drivers/misc/mediatek/Makefile.custom

ccflags-y += -I$(srctree)/drivers/misc/mediatek/video/ \
             -I$(srctree)/drivers/misc/mediatek/videox/$(MTK_PLATFORM) \
             -I$(srctree)/drivers/misc/mediatek/cmdq/$(MTK_PLATFORM) \
             -I$(srctree)/drivers/misc/mediatek/cmdq

ifeq ($(CONFIG_MTK_SEC_VIDEO_PATH_SUPPORT),y)
ifeq ($(CONFIG_TRUSTONIC_TEE_SUPPORT),y)
ccflags-y += \
	 -I$(srctree)/drivers/misc/mediatek/gud/$(MTK_PLATFORM)/gud/MobiCoreKernelApi/public \
	 -I$(srctree)/drivers/misc/mediatek/gud/$(MTK_PLATFORM)/gud/MobiCoreKernelApi/include \
	 -I$(srctree)/../vendor/trustonic/platform/$(MTK_PLATFORM)/trustlets/tplay/Tltplay/public

endif
endif

#driver
obj-y += ddp_ovl.o
obj-y += ddp_color.o
obj-y += ddp_rdma.o
obj-y += ddp_wdma.o
obj-y += ddp_aal.o
obj-y += ddp_pwm.o
obj-y += ddp_gamma.o
obj-y += ddp_dither.o
#obj-y += ddp_od.o
obj-y += ddp_dsi.o
obj-y += ddp_dpi.o
#obj-y += ddp_split.o
obj-y += ddp_ufoe.o

#common		
obj-y += ddp_drv.o
obj-y += ddp_path.o
obj-y += ddp_debug.o
obj-y += ddp_dump.o

obj-y += ddp_manager.o
obj-y += ddp_irq.o
obj-y += ddp_info.o
obj-y += ddp_color_format.o

obj-y += data_rgb888_64x64.o
obj-y += data_rgb888_64x64_golden.o

obj-y += ddp_mmp.o
obj-y += ddp_met.o

#should remove
obj-y += ddp_misc.o

obj-y += display_recorder.o

ifeq ($(CONFIG_MMPROFILE),y)
ccflags-y += -DDEFAULT_MMP_ENABLE
endif

ifeq ($(TARGET_BUILD_VARIANT),user)
ccflags-y += -D_MTK_USER_
endif

ifeq ($(MTK_MIRAVISION_SUPPORT), yes)
    ccflags-y += -DCONFIG_FOR_SOURCE_PQ
endif

ccflags-y += -DMET_USER_EVENT_SUPPORT 

# EOF
