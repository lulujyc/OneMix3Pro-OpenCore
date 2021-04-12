# OneMix3Pro-OpenCore
Install macOS on your 10th gen OneMix 3 minibooks.

EOL Notice: I don't have the hardware anymore so the support for this EFI configuration is ended until someone forks it.

## Compatibility

- **OneMix 3 Pro Koi/ Platinum/ Black with i7 10510Y**: The main model this configuration was developed with and for.
- **OneMix 3 Pro Black with i5 10210Y**: Compatible in theory. Not tested.
- **OneMix 3s Black/ Platinum/ Pink with i3 10110Y** Compatible in theory. Not tested.
 
## Post-installation tweaks
A few required or otherwise useful steps to take on a running macOS system on your OneMix:

**Using your own serial number**

Just generate a new set with OpenCore Configurator and you're good to go

**Changing the display orientation**

To correct the display orientation within macOS, press and hold down `cmd+opt` (`Windows+alt`) and open `System Preferences`. Keep holding down those two buttons and click on `Displays`. The screen orientation option will now appear even for the built-in display. Set it to `90 degrees` for the correct orientation. Alternatively...just download the [Display Rotation Menu](https://www.magesw.com/displayrotation/) app and set the view to portrait flipped

**Disabling Power-related Settings**

In order to achieve a stable sleep, you're responsible of disabling the following:
- Power Nap (if available)
- Wake for Internet Access
- tcpkeepalive (hint: `sudo pmset -a tcpkeepalive 0`)

**Switching `cmd` and `opt`**

In keyboard settings, select the modifier keys option, and switch `cmd` (win) with `opt` (alt)

**Brightness Control**

Use `Brightness Slider` from App Store. Partially works but it's inverted. Alternatively check out the BrightnessX app and use F1/ F2 to increase/ lower the brightness. Unfortunately native brightness control isn't supported at this moment, interested developers might want to take a look at the DSDT and PNLF.

## What works

- Full hardware acceleration, faked UHD617 Amber Lake-Y
- Audio
- Battery reading and charging recognition
- USB-A port as-well as the USB-C port
- CPU Temperature and voltage/wattage reading
- Internal Wi-Fi via OpenIntelWireless (Big Sur Support)
- Bluetooth via OpenIntelWireless
- Sleep
- Touchscreen

## What's untested

- Hibernation
- HDMI output

## What's not yet working

- Microphone

## What will never* work

- Intel SD Card Reader
- Bosch Accelerometer
- Focaltech Fingerprint

_* Not unless someone decides to make custom kexts for these, of course._
