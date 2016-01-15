Hello All 

This is all my experience patch DSDT,SSDT(AppleHDA,Graphics,Battery,Brighness,Slep...) for Dell 7447
Only one step Copy file ./DSDT.aml to patched(clover)
Note that with audio
	0. If S/L/E not have AppleHDA.kext copy AppleHDA....ALC255/AppleHDA.kext to S/L/E
	1. Use HVT(hackintosh vietnam tool) to patch ALC255. Patch DSDT with layout :28 (0x1C)
	2. Copy config.plist to Clover(not have boot/audio in clover)
	3. copy file com.apple.Boot.plist to \Library\Preferences\SystemConfiguration
	4. Run Kext utility-> Enjoy -> Reboot
	5. If not work do again with step 4
How to fix Sleep(when use usb wifi):
	1. install package sleepwatcher : brew install sleepwatcher. End make sure brew doctor(not have problem(not link))
	2. cp rc.* /etc/ (Edit MAC USB WIFI)
		Content of rc.sleep:
		#!/bin/sh
		osascript -e 'quit app "Wireless Network Utility"'
		echo "1" > /Applications/Wireless\ Network\ Utility.app/c4e984143a23rfoff.rtl
		open -a "Wireless Network Utility"
		Content of rc.wakeup:
		#!/bin/sh
		osascript -e 'quit app "Wireless Network Utility"'
		echo "0" > /Applications/Wireless\ Network\ Utility.app/c4e984143a23rfoff.rtl
		open -a "Wireless Network Utility"
			
