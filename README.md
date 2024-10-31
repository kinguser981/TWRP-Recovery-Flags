# TWRP-Recovery-Flags
TWRP-Recovery-Flags

```
# Automatically implies these:
BOARD_HAS_NO_REAL_SDCARD := true

TW_USE_TOOLBOX := true

TW_EXCLUDE_SUPERSU := true

TW_EXCLUDE_MTP := true

TW_OEM_BUILD := true

# Add EXT4 support
TARGET_USERIMAGES_USE_EXT4 := true

# Disable/enable SELinux. Only suggested when you want to enable SELinux support
TWHAVE_SELINUX := true

# Remove MTP support
TW_EXCLUDE_MTP := true

# No screen timeout
TW_NO_SCREEN_TIMEOUT := true

# disables things like sdcard partitioning and may save you some space if TWRP isn't fitting in your recovery patition
BOARD_HAS_NO_REAL_SDCARD := true

# this enables proper handling of /data/media on devices that have this folder for storage (most Honeycomb and devices that originally shipped with ICS like Galaxy Nexus
RECOVERY_SDCARD_ON_DATA := true

# HTC Dumlock for those devices which need it
TW_INCLUDE_DUMLOCK := true

TW_INTERNAL_STORAGE_PATH

TW_INTERNAL_STORAGE_MOUNT_POINT

TW_EXTERNAL_STORAGE_PATH

TW_EXTERNAL_STORAGE_MOUNT_POINT

# If your device has recovery as a second ramdisk of boot.img
TW_HAS_NO_RECOVERY_PARTITION := true

# To prevent /boot partition not found error
TW_HAS_NO_BOOT_PARTITION := true

# Removes the 'Reboot bootloader' button
TW_NO_REBOOT_BOOTLOADER := true

# Removes the 'Reboot recovery' button
TW_NO_REBOOT_RECOVERY := true

# Disable the battery percentage for devices where it doesn't work properly
TW_NO_BATT_PERCENT := true

# Same as above, for CPU Temperature
TW_NO_CPU_TEMP := true

# Allows you to map a custom keycode for power button, takes in a number, usually three digits
TW_CUSTOM_POWER_BUTTON := 107

# Always use rm -rf to wipe
TW_ALWAYS_RMRF := true

# Prevent TWRP from unmounting /system
TW_NEVER_UNMOUNT_SYSTEM := true

# Removes USB Storage capability
TW_NO_USB_STORAGE := true

# Inject TWRP as a second ramdisk for Samsung devices, which keep recoveries that way.
TW_INCLUDE_INJECTTWRP := true

TW_INCLUDE_BLOBPACK -- NEED HELP

# Specify a path to the lun file on device
TARGET_USE_CUSTOM_LUN_FILE_PATH := "/sys/class/android_usb/android0/f_mass_storage/lun0/file"

# Not very sure, I guess it allows you to simply pop in the lunfile itself
BOARD_UMS_LUNFILE :=

TW_HAS_DOWNLOAD_MODE -- For Samsung devices

TW_NO_SCREEN_BLANK -- NEED HELP

TW_SDEXT_NO_EXT4 -- Blocks EXT4 FS for SD-EXT partitions

# Forces use of /proc/cpuinfo for determining device id. Look here : https://github.com/omnirom/android_bootable_recovery/blob/android-6.0/data.cpp#l183-l184
TW_FORCE_CPUINFO_FOR_DEVICE_ID := true

# For older devices. See here :https://github.com/omnirom/android_bootable_recovery/blob/android-6.0/Android.mk#l383
TW_NO_EXFAT_FUSE := true

# Decryption support for /data
TW_INCLUDE_CRYPTO -- General decryption modules

# On some device, TWRP backup folder name will show 0000000000 bcos cpuinfo has no serial number. Using this flag then it will use ro.product.model as the folder name instead of all 0000000000
TW_USE_MODEL_HARDWARE_ID_FOR_DEVICE_ID := true

# Set the path to the sysfs entry which controls the brightness
TW_BRIGHTNESS_PATH := /sys/devices/platform/s3c24xx-pwm.0/pwm-backlight.0/backlight/pwm-backlight.0/backlight

# A seconday path for the above
TW_SECONDARY_BRIGHTNESS_PATH :=

# Max brightness to prevent display damage
TW_MAX_BRIGHTNESS := 255

# Default brightness for TWRP
TW_DEFAULT_BRIGHTNESS := 150

# Custom battery readout path, don't use the given path though, it is intended to be used for a full diagnostic.
TW_CUSTOM_BATTERY_PATH := /sys/class/power_supply/battery/batt_attr_text

# CPU temp sysfs path, if it is zero all the time.
TW_CUSTOM_CPU_TEMP_PATH := true

# Remove the ability to encrypt backups with a password
TW_EXCLUDE_ENCRYPTED_BACKUPS := true

# Timezone fixes for some Qcom devices.
TARGET_RECOVERY_QCOM_RTC_FIX

TW_NO_LEGACY_PROPS -- NEED HELP

# Supply a custom init.rc for the recovery
TARGET_RECOVERY_INITRC := device/htc/pico/ramdisk/recovery/init.recovery.rc

# Set the default language, if not english
TW_DEFAULT_LANGUAGE := en-US

# Specify architecture
TARGET_ARCH := arm

# For people who would want to have ToyBox rather than Busybox
TW_USE_TOOLBOX := true

# Remove exFAT formatting binaries
TW_NO_EXFAT := true

# Remove SuperSU and stop TWRP prompts to install it
TW_EXCLUDE_SUPERSU := true

# An awesome way to take screenshots. Back-end improvement, no noticeable user side changes. Screenshots work without it too
TW_INCLUDE_FB2PNG := true

BOARD_USES_BML_OVER_MTD -- NEED HELP

# include Logcat daemon for help in debugging
TWRP_INCLUDE_LOGCAT := true

# See here : https://github.com/omnirom/android_bootable_recovery/blob/android-6.0/Android.mk#L435
TARGET_RECOVERY_DEVICE_MODULES := true

TARGET_USERIMAGES_USE_F2FS -- Include mkfs.f2fs for formatting partitions as F2FS

# Include a custom hardwarekeyboard.cpp . Can't see the point though.
TWRP_CUSTOM_KEYBOARD := device/lge/hammerhead/recovery/hardwarekeyboard.cpp

# Log touch input
TWRP_EVENT_LOGGING := true

# @yuwneg :My experience on MTK tablet, typical is RECOVERY_TOUCHSCREEN_SWAP_XY & RECOVERY_TOUCHSCREEN_FLIP_Y is use is pair as MTK vendor tend to use landscape LCD but a normal portrait Touch Screen !
TW_X_OFFSET -- X-Axis offset for borked displays
TW_Y_OFFSET -- Y-Axis offset for borked displays

# Smartwatch optimisation
TW_ROUND_SCREEN := true

TW_THEME -- New flag, takes in the following : portrait_mdpi, landscape_mdpi, portrait_hdpi,landscape_hdpi,watch_mdpi . It should be caps but when I was compiling a minute ago, it threw me an error and asked to de-caps it. So, see for yourself what works

TW_CUSTOM_THEME -- Use a custom theme like materialised by @z31s1g . Give the path to the contents here.

TWRP_NEW_THEME -- Old is gold. Put false to use the old one.

TW_EXTRA_LANGUAGES -- Set to true and enable localisation

TW_MTP_DEVICE -- Specify a custom device name for MTP

TW_TARGET_USES_QCOM_BSP -- Qcom specific enhancements

TARGET_PREBUILT_KERNEL -- Use a prebuilt kernel rather than building from source

TARGET_RECOVERY_PIXEL_FORMAT -- Use RGBA,RGBX,ARGB and whatever, I don't remember, see the main thread for that info.

TARGET_RECOVERY_OVERSCAN_PERCENT -- Defines the padding to leave around the screen edges

BOARD_USE_CUSTOM_RECOVERY_FONT -- Specify a .ttf file to use as default font

BOARD_CUSTOM_GRAPHICS -- include customised graphics backends if 3.0.0-0 broke stuff for you

TARGET_CUSTOM_KERNEL_HEADERS -- NEED HELP

TW_NEW_ION_HEAP -- NEED HELP

RECOVERY_TOUCHSCREEN_SWAP_XY 
RECOVERY_TOUCHSCREEN_FLIP_X
RECOVERY_TOUCHSCREEN_FLIP_Y

RECOVERY_GRAPHICS_FORCE_USE_LINELENGTH -- Fixes slanty graphics

TW_DISABLE_DOUBLE_BUFFERING -- NEED HELP

TARGET_RECOVERY_FORCE_PIXEL_FORMAT -- NEED HELP FOR POSSIBLE INPUTS

BOARD_HAS_FLIPPED_SCREEN -- For people whose screens were mounted the wrong side across

TW_IGNORE_MAJOR_AXIS_0 -- NEED HELP

TW_IGNORE_MT_POSITION_0 -- NEED HELP

TW_IGNORE_ABS_MT_TRACKING_ID -- NEED HELP

TW_INPUT_BLACKLIST -- NEED HELP

TW_WHITELIST_INPUT -- NEED HELP

TARGET_HW_DISK_ENCRYPTION -- NEED HELP

TW_HAVE_X86_ACCELERATED_PIXELFLINGER -- Improvements for x86 based devices

ARCH_ARM_HAVE_NEON -- Take advantage of ARM-NEON optimisations

# remove TrueType fonts
TW_DISABLE_TTF:= true

# building of an OEM friendly TWRP. excludes SuperSu, uses Toolbox instead busybox, disables themeing. MORE INFOS TO BE ADDED
TW_OEM_BUILD := true

# Adds EXT4 formatting binaries
TARGET_USERIMAGES_USE_EXT4 := true

# exclude mtp from twrp (disable if you are not able to fix it device/kernel side, safes some space)
TW_EXCLUDE_MTP := true

# screen will stay awake
TW_NO_SCREEN_TIMEOUT := true

# needed on devices without a recovery partition (some devices have recovery included im boot.img)
TW_HAS_NO_RECOVERY_PARTITION := true

# removes the reboot option to boot into boooader, needed e.g. on samsung devices which use Download mode instead
TW_NO_REBOOT_BOOTLOADER := true

# add an option in reboot menu to reboot into Download Mode
TW_HAS_DOWNLOAD_MODE := true

# some devices don't have a temp sensor, disable in such case to stop spamming recovery.log
TW_NO_CPU_TEMP := true

# recursive delete by default instead fotmatting (available optional inside recovery settings too)
TW_ALWAYS_RMRF := true

# system won't be unmounted,
TW_NEVER_UNMOUNT_SYSTEM := true

# don't blank screen (available optional inside recovery settings too)
TW_NO_SCREEN_BLANK := true

# deprecated, use TW_INCLUDE_CRYPTO instead
TW_INCLUDE_JB_CRYPTO := true

# add support for encryption
TW_INCLUDE_CRYPTO := true

# use a custom init.rc in recovery, add the path. Example:
TARGET_RECOVERY_INITRC := device/samsung/p3100/rootdir/init.twrp.rc

# ToyBox (disables busybox?)
TW_USE_TOOLBOX := true

# exclude SuperSu e.g. to save some space or for different other reasons (supersu still included bx default?)
TW_EXCLUDE_SUPERSU := true

# include f2fs support (make sure your kernel supports f2fs!)
TARGET_USERIMAGES_USE_F2FS := true

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

# auto copy files placed in device/$VENDOR/$DEVICENAME/recovery/root inside recovery ramdisk (e.g. init.recivery*.rc which get removed from recoveryramdisk by default). example:
TARGET_RECOVERY_DEVICE_DIRS += device/samsung/espresso-common

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

# this one is used to replace the stocktheme with a different one (like material-play) the theme will be directly in ramdisk
TW_CUSTOM_THEME := /path/to/theme/

#adds ability to inject TWRP into some Samsung boot images for Samsung devices that have recovery as a second ramdisk in the boot image
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

# Add EXT4 support
TARGET_USERIMAGES_USE_EXT4 := true

# Disable/enable SELinux. Only suggested when you want to enable SELinux support
TWHAVE_SELINUX := true

# Remove MTP support
TW_EXCLUDE_MTP := true

# No screen timeout
TW_NO_SCREEN_TIMEOUT := true

# disables things like sdcard partitioning and may save you some space if TWRP isn't fitting in your recovery patition
BOARD_HAS_NO_REAL_SDCARD := true

# this enables proper handling of /data/media on devices that have this folder for storage (most Honeycomb and devices that originally shipped with ICS like Galaxy Nexus
RECOVERY_SDCARD_ON_DATA := true

# HTC Dumlock for those devices which need it
TW_INCLUDE_DUMLOCK := true

# If your device has recovery as a second ramdisk of boot.img
TW_HAS_NO_RECOVERY_PARTITION := true

# To prevent /boot partition not found error
TW_HAS_NO_BOOT_PARTITION := true

# Removes the 'Reboot bootloader' button
TW_NO_REBOOT_BOOTLOADER := true

# Removes the 'Reboot recovery' button
TW_NO_REBOOT_RECOVERY := true

# Disable the battery percentage for devices where it doesn't work properly
TW_NO_BATT_PERCENT := true

# Same as above, for CPU Temperature
TW_NO_CPU_TEMP := true

# Allows you to map a custom keycode for power button, takes in a number, usually three digits
TW_CUSTOM_POWER_BUTTON := 107

# Always use rm -rf to wipe
TW_ALWAYS_RMRF := true

# Prevent TWRP from unmounting /system
TW_NEVER_UNMOUNT_SYSTEM := true

# Removes USB Storage capability
TW_NO_USB_STORAGE := true

# Automatically implies these:
BOARD_HAS_NO_REAL_SDCARD := true

TW_USE_TOOLBOX := true

TW_EXCLUDE_SUPERSU := true

TW_EXCLUDE_MTP := true

TW_OEM_BUILD := true

# Inject TWRP as a second ramdisk for Samsung devices, which keep recoveries that way.
TW_INCLUDE_INJECTTWRP := true

# Specify a path to the lun file on device
TARGET_USE_CUSTOM_LUN_FILE_PATH := "/sys/class/android_usb/android0/f_mass_storage/lun0/file"

# Forces use of /proc/cpuinfo for determining device id. Look here : https://github.com/omnirom/android_b....cpp#l183-l184
TW_FORCE_CPUINFO_FOR_DEVICE_ID := true

# For older devices. See here :https://github.com/omnirom/android_b...ndroid.mk#l383
TW_NO_EXFAT_FUSE := true

# Decryption support for /data
TW_INCLUDE_CRYPTO := true

# On some device, TWRP backup folder name will show 0000000000 bcos cpuinfo has no serial number. Using this flag then it will use ro.product.model as the folder name instead of all 0000000000
TW_USE_MODEL_HARDWARE_ID_FOR_DEVICE_ID := true

# Set the path to the sysfs entry which controls the brightness
TW_BRIGHTNESS_PATH := /sys/devices/platform/s3c24xx-pwm.0/pwm-backlight.0/backlight/pwm-backlight.0/backlight

# A seconday path for the above
TW_SECONDARY_BRIGHTNESS_PATH := your phone's brightness path

# Max brightness to prevent display damage
TW_MAX_BRIGHTNESS := 255

# Default brightness for TWRP
TW_DEFAULT_BRIGHTNESS := 150

# Custom battery readout path, don't use the given path though, it is intended to be used for a full diagnostic.
TW_CUSTOM_BATTERY_PATH := /sys/class/power_supply/battery/batt_attr_text

# CPU temp sysfs path, if it is zero all the time.
TW_CUSTOM_CPU_TEMP_PATH := true

# Remove the ability to encrypt backups with a password
TW_EXCLUDE_ENCRYPTED_BACKUPS := true

# Supply a custom init.rc for the recovery
TARGET_RECOVERY_INITRC := device/htc/pico/ramdisk/recovery/init.recovery.rc

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

# Remove SuperSU and stop TWRP prompts to install it
TW_EXCLUDE_SUPERSU := true

# An awesome way to take screenshots. Back-end improvement, no noticeable user side changes. Screenshots work without it too
TW_INCLUDE_FB2PNG := true

# include Logcat daemon for help in debugging
TWRP_INCLUDE_LOGCAT := true

# See here : https://github.com/omnirom/android_b...ndroid.mk#L435
TARGET_RECOVERY_DEVICE_MODULES := true

# Include a custom hardwarekeyboard.cpp . Can't see the point though.
TWRP_CUSTOM_KEYBOARD := device/lge/hammerhead/recovery/hardwarekeyboard.cpp

# Log touch input
TWRP_EVENT_LOGGING := true

# Smartwatch optimisation
TW_ROUND_SCREEN := true

# Remove TrueType fonts
TW_DISABLE_TTF:= true

# building of an OEM friendly TWRP. excludes SuperSu, uses Toolbox instead busybox, disables themeing. MORE INFOS TO BE ADDED
TW_OEM_BUILD := true

# exclude mtp from twrp (disable if you are not able to fix it device/kernel side, safes some space)
TW_EXCLUDE_MTP := true

# screen will stay awake
TW_NO_SCREEN_TIMEOUT := true

# needed on devices without a recovery partition (some devices have recovery included im boot.img)
TW_HAS_NO_RECOVERY_PARTITION := true

# removes the reboot option to boot into boooader, needed e.g. on samsung devices which use Download mode instead
TW_NO_REBOOT_BOOTLOADER := true

# add an option in reboot menu to reboot into Download Mode
TW_HAS_DOWNLOAD_MODE := true

# some devices don't have a temp sensor, disable in such case to stop spamming recovery.log
TW_NO_CPU_TEMP := true

# recursive delete by default instead fotmatting (available optional inside recovery settings too)
TW_ALWAYS_RMRF := true

# system won't be unmounted,
TW_NEVER_UNMOUNT_SYSTEM := true

# don't blank screen (available optional inside recovery settings too)
TW_NO_SCREEN_BLANK := true

# deprecated, use TW_INCLUDE_CRYPTO instead
TW_INCLUDE_JB_CRYPTO := true

# add support for encryption
TW_INCLUDE_CRYPTO := true

# use a custom init.rc in recovery, add the path. Example:
TARGET_RECOVERY_INITRC := device/samsung/p3100/rootdir/init.twrp.rc

# ToyBox (disables busybox?)
TW_USE_TOOLBOX := true

# exclude SuperSu e.g. to save some space or for different other reasons (supersu still included bx default?)
TW_EXCLUDE_SUPERSU := true

# F2FS filesystem support (make sure your kernel supports f2fs!)
TARGET_USERIMAGES_USE_F2FS := true

# device resolution - deprecated, use TW_THEME instead
DEVICE_RESOLUTION := set your device's resolution

# define the theme for your device resolution, note: you can also use smaller/bigger themes because the theme get scaled for your deviceresolution anyway):
# TWRP Themes
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
# TWRP Custom Theme
TW_CUSTOM_THEME := /path/to/theme/

# auto copy files placed in device/$VENDOR/$DEVICENAME/recovery/root inside recovery ramdisk (e.g. init.recivery*.rc which get removed from recoveryramdisk by default). 
# example: for Nexus 5X ( set your device tree's location )
TARGET_RECOVERY_DEVICE_DIRS += device/lge/bulhead

# path to a prebuild kernel (can be used if you are unable to compile a kernel yourself, e.g. if no kernel source available)
TARGET_PREBUILT_KERNEL := $(LOCAL_PATH)/prebuilt/zImage

# swap x anf y axis for touch
RECOVERY_TOUCHSCREEN_SWAP_XY := true

# flip x axis for touch
RECOVERY_TOUCHSCREEN_FLIP_X := true

# flip y axis for touch,
RECOVERY_TOUCHSCREEN_FLIP_Y := true



```
