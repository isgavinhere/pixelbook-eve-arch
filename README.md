# pixelbook-eve-arch
Steps for getting arch linux running on the Google Pixelbook Eve (2017)

This is just a quick reference of the steps I took to get Arch Linux (June 2026 ISO) running on my i5 8gb ram 128gb eMMC Pixelbook.

Create a SuzyQ cable following the documentation here https://chromium.googlesource.com/chromiumos/third_party/hdctools/+/HEAD/docs/ccd.md
You can also just disconnect the battery while the laptop is running to disable the write protection however I wanted to brush up on my soldering skills so I bought the required components.

Follow the steps here on how to use the cable and disable write protection https://docs.mrchromebox.tech/docs/firmware/wp/disabling.html

Follow the steps here to flash the firmware with the custom UEFI to allow us to install Linux. https://docs.mrchromebox.tech/docs/fwscript.html

Install arch following the instructions on the arch linux wiki. Here I set up LUKS and had a separate root and home partition but how you set it up is totally up to you.

I ended up choosing GNOME as my DE, normally I'm a i3 or sway guy but I wanted to make use of the touch screen and tablet mode this laptop offers and tiling WMs just aren't really meant for this purpose.

Once it's installed, follow the steps here to get audio working. You may need to reboot the laptop afterwards. https://github.com/WeirdTreeThing/chromebook-linux-audio

To get the keyboard shortcuts remapped. Place the 61-eve-keyboard.hwdb file in this repo into your /etc/udev/hwdb/ directory and run systemd-hwdb update. Again you may need to reboot the laptop for it to reflect on your keyboard.

WORKING:
Wifi
Sound from speakers
Suspend
Webcam
Screen autobrightness (Though a bit distracting so I have it disabled from GNOME settings)
Screen brightness
Keyboard brightness

NOT TESTED (YET):
Bluetooth
USBC display out

TODO:
Enable secureboot
Have TPM unlock the LUKS partition automatically (May not be possible as the chromebook does not expose the full TPM2 functionality)
Fix USBC PD fast charging (It appears to charge at a very slow rate but fast charging works when laptop is shutdown)

