# Bootlogo Warnings Patcher
### A simple tool to get rid of [annoying boot warnings](https://imgur.com/a/FFeOHkC) - exynos only
```
Copyright 2020-2021 © corsicanu
Licensed under CC BY-NC-SA 4.0
https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode
```
### Disclaimer
```
I am not responsable for anything you do with your device, don't blame me or anyone else 
involved in this for your failures, you are the only one choosing to mess up with your device. 
```
### Supported devices
   - Galaxy S21 Series - G991B G996B G998B G991N G996N G998N
   - Galaxy S20 Series - G980F G985F G981B G986B G988B
   - Galaxy S10 Series - G970F G973F G975F G977B G970N G973N G975N G977N
   - Galaxy Note 20 Series - N980F N981B N985F N986B
   - Galaxy Note 10 Series - N970F N975F N976B N971N N976N
   - Galaxy A\*0 Series - A105F/FN A205F/FN A305F/FN A405F/FN A505F/FN
   - Galaxy M\*1 Series - M215F M315F
   - Galaxy Tab A 10.1 (2019) - T510 T515

### Instructions:
   - Download TWRP_Bootlogo_patcher-*.zip from [releases](https://github.com/corsicanu/TWRP_Bootlogo_patcher/releases)
   - Boot phone in TWRP
   - Flash the downloaded zip as any other
   - Reboot and enjoy

### Further info:
   - If your **exynos** device is not present in the list above, create an [issue](https://github.com/corsicanu/TWRP_Bootlogo_patcher/issues) and tell me more about your device (Model number & possible model variations - F/FN/N/+/e/Ultra/Nfc and so on)
   - In case of reflashing modem/bootloader you will need to reflash this zip to nuke the warnings again (bootloader will overwrite the patch)
   - Any graphical glitch regarding the bootlogo, or any other exotic issue, will be fixed by reflashing bootloader of the specific software version you are running, however, in case you encounter any of those try to submit an [issue](https://github.com/corsicanu/TWRP_Bootlogo_patcher/issues) in which i'll try to assist in fixing

### Patch steps (for nerds):
   - get the device bootloader version from cmdline
   - if the bootloader version matches device list - proceed to patch
   - unpack tools and prepare folders
   - find up_param and param blocks and set them as variables
   - check up_param for [booting_warning.jpg](https://i.imgur.com/PMDv38E.jpeg)
       - if booting_warning.jpg size is greater than 1byte then it means it's not patched
       - backup up_param to internal storage
       - copy normal splash logo over [svb_orange.jpg](https://i.imgur.com/bQ9wTeW.jpeg)
       - echo "" (nothing) in booting_warning.jpg (which makes the size of the file 1byte)
       - repack up_param and flash back
   - check param for [booting_warning.jpg](https://i.imgur.com/PMDv38E.jpeg)
       - if booting_warning.jpg size is greater than 1byte then it means it's not patched
       - backup param to internal storage
       - copy normal splash logo over [svb_orange.jpg](https://i.imgur.com/bQ9wTeW.jpeg)
       - echo "" (nothing) in booting_warning.jpg (which makes the size of the file 1byte)
       - repack param and flash back

With these phone now will show a "nothing" logo and then show a warning containing the normal splash logo, which will make it look as normal and unrooted/locked bootloader. 

Yes, the warnings are not disabled, more like hidden, the phone will take same time as before to pass the splash screen but at least you won't have the hazard triangle which looks like it's soon going to explode (inb4 Note7, we will miss you).
