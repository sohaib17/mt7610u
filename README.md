**MT7610U**

These drivers are based on vendor chipset drivers. Most of the modifications are taken from TP-Link drivers and various blogs. The list of modifications include:
* Patch to add support for kernel > 3.x
* Added Archer T2U device ID
* Suppressed unused variables/functions warnings
* Enabled WPA supplicant
* There are some other changes copied from Coredy AE600 drivers

Build:
* Set the following variables in bash:
    * $KSRC           # path to kernel source
    * $TARGET_ARCH    # architecture, in my case it was arm
    * $TARGET_PREFIX  # path to the toolchain for cross compiling
* While in driver directory, run 'make' to build mt7610u.ko module
* Read the 'README_STA_usb' to load the module and dependencies

Note:

I tested this on OpenELEC 6.0 and the module was working fine for 2.4GHz.
But dmesg shows an error while loading RT2780STA.DAT, the log can be seen at: http://pastebin.com/T1ZHimJc
