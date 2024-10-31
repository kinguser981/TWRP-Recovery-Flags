# TWRP-Recovery-Flags
TWRP Recovery Flags By Samuel Kendall

```
# Copyright (C) 2024 The TWRP Open Source Project
```

```


# Statusbar icons flags
TW_STATUS_ICONS_ALIGN := center

#
TW_CUSTOM_CPU_POS := 50

#
TW_CUSTOM_CLOCK_POS := 300

#
TW_CUSTOM_BATTERY_POS := 800

#
BOARD_KERNEL_SEPARATED_DTBO := true

#
BOARD_INCLUDE_RECOVERY_DTBO := true

# KERNEL IMAGE NAME
BOARD_KERNEL_IMAGE_NAME := Image

# 
BOARD_INCLUDE_DTB_IN_BOOTIMG

# for device without dedicated recovery partition 
BOARD_USES_RECOVERY_AS_BOOT := true

# Workaround for error copying vendor files to recovery ramdisk
BOARD_VENDORIMAGE_FILE_SYSTEM_TYPE := ext4
TARGET_COPY_OUT_VENDOR := vendor

# Maintainer name or device Version
TW_DEVICE_VERSION := Nokia 5.3

# Metadata
BOARD_USES_METADATA_PARTITION := true
BOARD_ROOT_EXTRA_FOLDERS += metadata

#
TW_OVERRIDE_SYSTEM_PROPS := \
    "ro.build.product;ro.build.fingerprint=ro.system.build.fingerprint;ro.build.version.incremental;ro.product.device=ro.product.system.device;ro.product.model=ro.product.system.model;ro.product.name=ro.product.system.name"

#
TW_FORCE_KEYMASTER_VER := true

# For A/B devices that has dedicated recovery, removing that option in Advance.
TW_NO_FLASH_CURRENT_TWRP := true

# Platform Version
PLATFORM_VERSION := 99.87.36
PLATFORM_VERSION_LAST_STABLE := $(PLATFORM_VERSION)

#
BOARD_KERNEL_CMDLINE := androidboot.hardware=qcom androidboot.console=ttyMSM0 androidboot.memcg=1 lpm_levels.sleep_disabled=1 video=vfb:640x400,bpp=32,memsize=3072000 msm_rtb.filter=0x237 service_locator.enable=1 swiotlb=1 earlycon=msm_geni_serial,0x4a90000 loop.max_part=7 cgroup.memory=nokmem,nosocket

#
BOARD_HAS_LARGE_FILESYSTEM := true

# Build Rules
BUILD_BROKEN_DUP_RULES := true

#
BUILD_BROKEN_ELF_PREBUILT_PRODUCT_COPY_FILES := true

# All the partitions to be wiped (in order) under recovery.
# Wipe the boot partitions last so that all partitions will be wiped
# correctly even if the wiping process gets interrupted by a force boot.
TARGET_RECOVERY_WIPE := device/samsung/a05s/recovery.wipe

recovery.wipe file content >>>
##########################################################
/dev/block/bootdevice/by-name/userdata
/dev/block/by-name/userdata
/dev/block/bootdevice/by-name/metadata
/dev/block/by-name/metadata
/dev/block/bootdevice/by-name/system_a
/dev/block/bootdevice/by-name/system_b
/dev/block/bootdevice/by-name/vendor_a
/dev/block/bootdevice/by-name/vendor_b
/dev/block/bootdevice/by-name/userdata
/dev/block/bootdevice/by-name/boot_a
/dev/block/bootdevice/by-name/boot_b
########################################################

# Hack: prevent anti rollback
PLATFORM_SECURITY_PATCH := 2099-12-31
VENDOR_SECURITY_PATCH := 2099-12-31

# Vendor Properties
TARGET_VENDOR_PROP += $(DEVICE_PATH)/vendor.prop

# Kernel Modules
TW_LOAD_VENDOR_MODULES := "*"

TW_LOAD_VENDOR_BOOT_MODULES := true

#
TW_LOAD_VENDOR_MODULES_EXCLUDE_GKI := true

# To INCLUDE FASTBOOTD
TW_INCLUDE_FASTBOOTD := true

# To Exclude DEFAULT USB INIT
TW_EXCLUDE_DEFAULT_USB_INIT := true

# To Exclude TWRPAPP
TW_EXCLUDE_TWRPAPP := true

# mke2fs
TARGET_USES_MKE2FS := true

# Kernel Configuration
BOARD_BOOTIMG_HEADER_VERSION := 2
TARGET_FORCE_PREBUILT_KERNEL := true
TARGET_PREBUILT_KERNEL := $(DEVICE_PATH)/prebuilt/kernel
TARGET_PREBUILT_DTB := $(DEVICE_PATH)/prebuilt/dtb.img
BOARD_PREBUILT_DTBOIMAGE := $(DEVICE_PATH)/prebuilt/dtbo.img

#
TARGET_KERNEL_CONFIG := a05s_defconfig

#
TARGET_KERNEL_SOURCE := kernel/samsung/a05s
TARGET_KERNEL_SOURCE := kernel/nokia/cap_sprout

# APEX
DEXPREOPT_GENERATE_APEX_IMAGE := true
TW_EXCLUDE_APEX := true

#
TARGET_RECOVERY_FSTAB := $(DEVICE_PATH)/recovery/root/system/etc/recovery.fstab

#
BOARD_SYSTEMIMAGE_PARTITION_TYPE := ext4

#
BOARD_USERDATAIMAGE_FILE_SYSTEM_TYPE := f2fs

#
BOARD_VENDORIMAGE_FILE_SYSTEM_TYPE := ext4

#
BOARD_VENDORIMAGE_FILE_SYSTEM_TYPE

# Properties
TARGET_SYSTEM_PROP += $(DEVICE_PATH)/system.prop

# Platform
TARGET_BOARD_PLATFORM :=

#
TARGET_BOOTLOADER_BOARD_NAME :=

#
QCOM_BOARD_PLATFORMS += 

#
BOARD_USES_FULL_RECOVERY_IMAGE

# Verified Boot
BOARD_AVB_ENABLE := true

#
TW_USE_FSCRYPT_POLICY

# Crypto
TW_INCLUDE_FBE_METADATA_DECRYPT := true

#
BOARD_USES_QCOM_FBE_DECRYPTION := true

#
TW_SUPPORT_INPUT_AIDL_HAPTICS := true

#
TW_SUPPORT_INPUT_AIDL_HAPTICS_FIX_OFF := true

# To load vendor dlkm modules 
TW_LOAD_VENDOR_DLKM_MODULES := "qpnp_adaptive_charge.ko stmicro_mmi.ko goodix_brl_mmi.ko qpnp-pbs.ko qcom-hv-haptics.ko utags.ko"

# Copy DTB
PRODUCT_COPY_FILES += \
        $(TARGET_PREBUILT_DTB):dtb.img

# Init
TARGET_INIT_VENDOR_LIB

# Display
TARGET_SCREEN_DENSITY := 450
TARGET_SCREEN_HEIGHT := 1080
TARGET_SCREEN_WIDTH := 1920

# Bootloader
TARGET_NO_BOOTLOADER := false

#
TARGET_USES_UEFI := true

#
TARGET_USES_REMOTEPROC := true

#
AB_OTA_PARTITIONS += \
    boot \
    dtbo \
    product \
    system 

#
DEVICE_PREBUILT_PATH := device/motorola/eqe/prebuilt

# A/B
AB_OTA_UPDATER := true

# System as root
BOARD_BUILD_SYSTEM_ROOT_IMAGE := true

#
BOARD_SUPPRESS_SECURE_ERASE := true

# For building with minimal manifest
ALLOW_MISSING_DEPENDENCIES := true

# Specifies additional kernel command-line parameters.
BOARD_KERNEL_CMDLINE

# Determines whether the device uses a metadata partition.
BOARD_USES_METADATA_PARTITION

# Sets the device's screen resolution.
DEVICE_RESOLUTION

# Configure touchscreen rotation and mirroring.
RECOVERY_TOUCHSCREEN_FLIP_Y

# Defines the device's architecture (e.g., arm64).
TARGET_ARCH := arm64
TARGET_ARCH_VARIANT := armv8-a
TARGET_CPU_ABI := arm64-v8a
TARGET_CPU_ABI2 := 
TARGET_CPU_VARIANT := generic
TARGET_CPU_VARIANT_RUNTIME := generic

TARGET_2ND_ARCH := arm
TARGET_2ND_ARCH_VARIANT := armv7-a-neon
TARGET_2ND_CPU_ABI := armeabi-v7a
TARGET_2ND_CPU_ABI2 := armeabi
TARGET_2ND_CPU_VARIANT := generic
TARGET_2ND_CPU_VARIANT_RUNTIME := cortex-a9

# Assert
TARGET_OTA_ASSERT_DEVICE := RMX2185,rmx2185

# Lists additional modules to include in the recovery image.
# Additional binaries & libraries needed for recovery
TARGET_RECOVERY_DEVICE_MODULES += \
    libkeymaster4 \
    libpuresoftkeymasterdevice \
    ashmemd_aidl_interface-cpp \
    libashmemd_client

# RECOVERY ADDITIONAL RELINK LIBRARY FILES
TW_RECOVERY_ADDITIONAL_RELINK_LIBRARY_FILES += \
    $(TARGET_OUT_SHARED_LIBRARIES)/libkeymaster4.so \
    $(TARGET_OUT_SHARED_LIBRARIES)/libpuresoftkeymasterdevice.so \
    $(TARGET_OUT_SHARED_LIBRARIES)/ashmemd_aidl_interface-cpp.so \
    $(TARGET_OUT_SHARED_LIBRARIES)/libashmemd_client.so

# Determine the file systems used for userdata, system, and other partitions.
TARGET_USES_MKE2FS

# Forces TWRP to use rm -rf when deleting files and directories.
TW_ALWAYS_RMRF

# Specify the paths to brightness control files.
TW_BRIGHTNESS_PATH

# Define custom paths for battery.
TW_CUSTOM_BATTERY_PATH

# Set the default brightness level.
TW_DEFAULT_BRIGHTNESS

# Specifies the device's version.
TW_DEVICE_VERSION

# Disables TrueType font rendering.
TW_DISABLE_TTF

# Exclude certain features from TWRP.
TW_EXCLUDE_DEFAULT_USB_INIT

# Forces TWRP to use CPU info for device ID.
TW_FORCE_CPUINFO_FOR_DEVICE_ID

# to set device display framerate
TW_FRAMERATE

# Configure the display's offset.
TW_H_OFFSET

# add it for Samsung devices 
TW_HAS_DOWNLOAD_MODE

# Indicate the presence of specific Emergency download mode.
TW_HAS_EDL_MODE

# To enable decryption.
TW_INCLUDE_CRYPTO_FBE

# Enable various features and tools in TWRP.
TW_INCLUDE_LIBRESETPROP

# Enable various features and tools in TWRP.
TW_INCLUDE_LPTOOLS

# 
TW_INCLUDE_NTFS_3G

# Enable various features and tools in TWRP.
TW_INCLUDE_REPACKTOOLS

# 
TW_INCLUDE_RESETPROP

# 
TW_NO_BIND_SYSTEM

# 
TW_NO_LEGACY_PROPS

# Enables support for round screens.
TW_ROUND_SCREEN

# Specifies the theme to use.
TW_THEME

# Enables the use of the new minadbd.
TW_USE_NEW_MINADBD

# Configure SELinux options.
TW_HAVE_SELINUX

# 
TARGET_NO_KERNEL := false

# Add EXT4 support
TARGET_USERIMAGES_USE_EXT4 := true

# disables things like sdcard partitioning and may save you some space if TWRP isn't fitting in your recovery patition
BOARD_HAS_NO_REAL_SDCARD := true

# this enables proper handling of /data/media on devices that have this folder for storage (most Honeycomb and devices that originally shipped with ICS like Galaxy Nexus
RECOVERY_SDCARD_ON_DATA := true

# HTC Dumlock for those devices which need it
TW_INCLUDE_DUMLOCK := true

#
TW_INTERNAL_STORAGE_PATH

#
TW_INTERNAL_STORAGE_MOUNT_POINT

#
TW_EXTERNAL_STORAGE_PATH

#
TW_EXTERNAL_STORAGE_MOUNT_POINT

# If your device has recovery as a second ramdisk of boot.img
TW_HAS_NO_RECOVERY_PARTITION := true

# To prevent /boot partition not found error
TW_HAS_NO_BOOT_PARTITION := true

# Removes the 'Reboot recovery' button
TW_NO_REBOOT_RECOVERY := true

# Disable the battery percentage for devices where it doesn't work properly
TW_NO_BATT_PERCENT := true

# Allows you to map a custom keycode for power button, takes in a number, usually three digits
TW_CUSTOM_POWER_BUTTON := 107

# Prevent TWRP from unmounting /system
TW_NEVER_UNMOUNT_SYSTEM := true

#
TW_INCLUDE_BLOBPACK

# Specify a path to the lun file on device
TARGET_USE_CUSTOM_LUN_FILE_PATH := "/sys/class/android_usb/android0/f_mass_storage/lun0/file"

# Not very sure, I guess it allows you to simply pop in the lunfile itself
BOARD_UMS_LUNFILE :=

# Blocks EXT4 FS for SD-EXT partitions
TW_SDEXT_NO_EXT4

# Decryption support for /data
TW_INCLUDE_CRYPTO

# On some device, TWRP backup folder name will show 0000000000 bcos cpuinfo has no serial number. Using this flag then it will use ro.product.model as the folder name instead of all 0000000000
TW_USE_MODEL_HARDWARE_ID_FOR_DEVICE_ID := true

# Max brightness to prevent display damage
TW_MAX_BRIGHTNESS := 255

# CPU temp sysfs path, if it is zero all the time.
TW_CUSTOM_CPU_TEMP_PATH := true

# Remove the ability to encrypt backups with a password
TW_EXCLUDE_ENCRYPTED_BACKUPS := true

# Timezone fixes for some Qcom devices.
TARGET_RECOVERY_QCOM_RTC_FIX

#
BOARD_USES_BML_OVER_MTD

# include Logcat for help in debugging
TWRP_INCLUDE_LOGCAT := true

# Configure the display's offset.
TW_X_OFFSET -- X-Axis offset for borked displays
TW_Y_OFFSET -- Y-Axis offset for borked displays

TW_THEME -- New flag, takes in the following : portrait_mdpi, landscape_mdpi, portrait_hdpi,landscape_hdpi,watch_mdpi . It should be caps but when I was compiling a minute ago, it threw me an error and asked to de-caps it. So, see for yourself what works

# Old is gold. Put false to use the old one.
TWRP_NEW_THEME

# Set to true and enable localisation
TW_EXTRA_LANGUAGES

# Specify a custom device name for MTP
TW_MTP_DEVICE

# Qcom specific enhancements
TW_TARGET_USES_QCOM_BSP

# Use RGBA,RGBX,ARGB and whatever, I don't remember, see the main thread for that info.
TARGET_RECOVERY_PIXEL_FORMAT

# Defines the padding to leave around the screen edges
TARGET_RECOVERY_OVERSCAN_PERCENT

# Specify a .ttf file to use as default font
BOARD_USE_CUSTOM_RECOVERY_FONT

# include customised graphics backends if 3.0.0-0 broke stuff for you
BOARD_CUSTOM_GRAPHICS

#
TARGET_CUSTOM_KERNEL_HEADERS

#  Fixes slanty graphics
RECOVERY_GRAPHICS_FORCE_USE_LINELENGTH

#
TW_DISABLE_DOUBLE_BUFFERING

# For people whose screens were mounted the wrong side across
BOARD_HAS_FLIPPED_SCREEN

#
TW_IGNORE_MAJOR_AXIS_0

#
TW_IGNORE_MT_POSITION_0

#
TW_IGNORE_ABS_MT_TRACKING_ID

#
TW_WHITELIST_INPUT

#
TARGET_HW_DISK_ENCRYPTION

# Improvements for x86 based devices
TW_HAVE_X86_ACCELERATED_PIXELFLINGER

# Take advantage of ARM-NEON optimisations
ARCH_ARM_HAVE_NEON

# building of an OEM friendly TWRP. excludes SuperSu, uses Toolbox instead busybox, disables themeing. MORE INFOS TO BE ADDED
TW_OEM_BUILD := true

# screen will stay awake
TW_NO_SCREEN_TIMEOUT := true

# add an option in reboot menu to reboot into Download Mode For Samsung devices
TW_HAS_DOWNLOAD_MODE := true

# don't blank screen (available optional inside recovery settings too)
TW_NO_SCREEN_BLANK := true

# exclude SuperSu e.g. to save some space or for different other reasons (supersu still included by default?)
TW_EXCLUDE_SUPERSU := true

# device resolution - deprecated, use TW_THEME instead
DEVICE_RESOLUTION :=

# define the theme for your device resolution, note: you can also use smaller/bigger themes because the theme get scaled for your deviceresolution anyway):

# 240x240 280x280 320x320
TW_THEME := watch_mdpi

# 320x480 480x800 480x854 540x960
TW_THEME := portrait_mdpi

# 720x1280 800x1280 1080x1920 1200x1920 1440x2560 1600x2560
TW_THEME := portrait_hdpi

# 800x480 1024x600 1024x768
TW_THEME := landscape_mdpi

# 1280x800 1920x1200 2560x1600
TW_THEME := landscape_hdpi

# device resolution - deprecated, use TW_THEME instead
DEVICE_RESOLUTION := set your device's resolution

# auto copy files placed in device/$VENDOR/$DEVICENAME/recovery/root inside recovery ramdisk (e.g. init.recivery*.rc which get removed from recoveryramdisk by default). example:
TARGET_RECOVERY_DEVICE_DIRS += device/samsung/espresso-common

# Use a prebuilt kernel rather than building from source
# path to a prebuild kernel (can be used if you are unable to compile a kernel yourself, e.g. if no kernel source available)
TARGET_PREBUILT_KERNEL := $(LOCAL_PATH)/prebuilt/zImage

# swap x anf y axis for touch
RECOVERY_TOUCHSCREEN_SWAP_XY := true

# flip x axis for touch
RECOVERY_TOUCHSCREEN_FLIP_X := true

# flip y axis for touch,
RECOVERY_TOUCHSCREEN_FLIP_Y := true

Gesendet von meinem LG-H815 mit Tapatalk

# don't include default init.recovery.usb.rc, provide your own or use needed defines inside init.recovery.$DEVICE.rc
TW_EXCLUDE_DEFAULT_USB_INIT := true

# TWRP Custom Theme
# this one is used to replace the stocktheme with a different one (like material-play) the theme will be directly in ramdisk
TW_CUSTOM_THEME := /path/to/theme/

# adds ability to inject TWRP into some Samsung boot images for Samsung devices that have recovery as a second ramdisk in the boot image
# Inject TWRP as a second ramdisk for Samsung devices, which keep recoveries that way.
TW_INCLUDE_INJECTTWRP := true

# this has sonething to do with 3.10 kernels and a different naming in /include/linux/ion.h ... like a switch between old heap_mask and new heap_id_mask
TW_NEW_ION_HEAP

# The only possible varible right now is RGB_565. BGRA_8888, RGBA_8888 and RGBX_8888 are not yet implemented.
TARGET_RECOVERY_FORCE_PIXEL_FORMAT
TARGET_RECOVERY_PIXEL_FORMAT := RGBX_8888
TARGET_RECOVERY_PIXEL_FORMAT := BGRA_8888

# Put it on the device and read the more verbose log to see what inputs you want to blacklist.
TWRP_EVENT_LOGGING := true

# TW_INPUT_BLACKLIST Usage:
TW_INPUT_BLACKLIST := accelerometer
TW_INPUT_BLACKLIST := "accelerometer\x0agyroscope"

# Disable/enable SELinux. Only suggested when you want to enable SELinux support
TWHAVE_SELINUX := true

# Removes USB Storage capability
TW_NO_USB_STORAGE := true

# For older devices. See here :https://github.com/omnirom/android_b...ndroid.mk#l383
TW_NO_EXFAT_FUSE := true

# Decryption support for /data
TW_INCLUDE_CRYPTO := true

# Set the path to the sysfs entry which controls the brightness
TW_BRIGHTNESS_PATH := /sys/devices/platform/s3c24xx-pwm.0/pwm-backlight.0/backlight/pwm-backlight.0/backlight

# A seconday path for the above
TW_SECONDARY_BRIGHTNESS_PATH := your phone's brightness path

# Custom battery readout path, don't use the given path though, it is intended to be used for a full diagnostic.
TW_CUSTOM_BATTERY_PATH := /sys/class/power_supply/battery/batt_attr_text

# Set the default language, if not english
TW_DEFAULT_LANGUAGE := en-US

# Specify architecture
# For arm
TARGET_ARCH := arm

# For arm64 
TARGET_ARCH := arm64

# For people who would want to have ToyBox rather than Busybox
TW_USE_TOOLBOX := true

# Remove exFAT formatting binaries
TW_NO_EXFAT := true

# An awesome way to take screenshots. Back-end improvement, no noticeable user side changes. Screenshots work without it too
TW_INCLUDE_FB2PNG := true

# Include a custom hardwarekeyboard.cpp . Can't see the point though.
TWRP_CUSTOM_KEYBOARD := device/lge/hammerhead/recovery/hardwarekeyboard.cpp

# Remove TrueType fonts
TW_DISABLE_TTF:= true

# exclude mtp from twrp (disable if you are not able to fix it device/kernel side, safes some space)
TW_EXCLUDE_MTP := true

# removes the reboot option to boot into boooader, needed e.g. on samsung devices which use Download mode instead
# Removes the 'Reboot bootloader' button
TW_NO_REBOOT_BOOTLOADER := true

# some devices don't have a temp sensor, disable in such case to stop spamming recovery.log
TW_NO_CPU_TEMP := true

# deprecated, use TW_INCLUDE_CRYPTO instead
TW_INCLUDE_JB_CRYPTO := true

# use a custom init.rc in recovery, add the path. Example:
TARGET_RECOVERY_INITRC := device/samsung/a05s/rootdir/init.twrp.rc
TARGET_RECOVERY_INITRC := device/htc/pico/ramdisk/recovery/init.recovery.rc

# F2FS filesystem support (make sure your kernel supports f2fs!)
TARGET_USERIMAGES_USE_F2FS := true

# auto copy files placed in device/$VENDOR/$DEVICENAME/recovery/root inside recovery ramdisk (e.g. init.recivery*.rc which get removed from recoveryramdisk by default). 
# example: for Nexus 5X ( set your device tree's location )
TARGET_RECOVERY_DEVICE_DIRS += device/lge/bulhead

```
