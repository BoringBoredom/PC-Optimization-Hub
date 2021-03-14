# How to persistently disable xHCI Interrupt Moderation
## This section is an extension of [Timecard's](https://github.com/djdallmann/GamingPCSetup/tree/master/CONTENT/RESEARCH/PERIPHERALS#q-can-you-define-the-interrupt-moderation-rate-for-usb-controllers-do-different-versions-of-windows-have-different-default-values) and [ucode's](https://www.overclock.net/threads/usb-polling-precision.1550666/page-61#post-28582024) guide and assumes having read those beforehand.
You can find the exact address by observing changes while moving the mouse <sup>1</sup>. Click on the associated IMOD value <sup>2</sup>, [convert](https://www.calculator.net/hex-calculator.html) the decimal number in the top left <sup>3</sup> to HEX and add it to the address <sup>4</sup>. In this example, adding C0 (192 dec) results in 00000000DF1320E4.

![](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/xhci%20imod/rwe.png)

RWEverything has a CLI you can use to automate the whole process at Startup. Press ***Windows key + r*** and type ***shell:startup***. Create a .bat file with the following content and replace ***PATH*** with the full path to RWEverything and ***ADDRESS*** with your address.

```
"PATH\Rw.exe" /Min /NoLogo /Stdout /Command="W16 0xADDRESS 0x0000"
```
