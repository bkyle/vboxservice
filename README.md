VBoxService
===========

VBoxService wraps VirtualBox VMs as a launchd compatible service.  In addition to being able to wrap a VirtualBox VM as a service, it can also be used to run a headless VM as a blocking process.

Usage: VBoxService [name]

Example launchd plist
=====================

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
  <key>Label</key>
	<string>vbox.myvm</string>
	<key>Program</key>
	<string>/usr/bin/VBoxService</string>
	<key>ProgramArguments</key>
	<array>
		<string>/usr/bin/VBoxService</string>
		<string>myvm</string>
	</array>
	<key>KeepAlive</key>
	<true/>
	<key>RunAtLoad</key>
	<true/>
	<key>StandardErrorPath</key>
  <string>/tmp/vbox.myvm.err</string>
  <key>StandardOutPath</key>
  <string>/tmp/vbox.myvm.out</string>
</dict>
</plist>


