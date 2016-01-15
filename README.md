Hello All 

This is all my experience patch DSDT,SSDT(AppleHDA,Graphics,Battery,Brighness,Slep...) for Dell 7447
Only one step Copy file ./DSDT.aml to patched(clover)
Note that with audio
	0. If S/L/E not have AppleHDA.kext copy AppleHDA....ALC255/AppleHDA.kext to S/L/E
	1. Use HVT(hackintosh vietnam tool) to patch ALC255
	2. Copy config.plist to Clover(not have boot/audio in clover)
	3. copy file com.apple.Boot.plist to \Library\Preferences\SystemConfiguration
	4. Run Kext utility-> Enjoy -> Reboot
	5. If not work do again with step 4
