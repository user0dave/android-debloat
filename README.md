# How To Android Debloat

This is a quick guide on how to get rid of unwanted applications on any android device. First you need to install adb (android debug bridge). For debian/ubuntu users this can be done by running the following command:
`$ sudo apt install android-tools-adb`

Now you need to enable USB-Debugging on your android device. If you have not enabled developer options on your device, go into settings -> about phone and hit the build number a couple of times to enable it. Then go into the developer options and enable USB-Debugging. Next connect your device to the computer. Make sure your computer has access to the data on the device (you may need to unlock the device). Open a terminal and type:
`$ adb shell`

Now you will be able to **list** all installed packages on the device via:
`$ pm list packages`or filter out a package with a specific name e.g. `$ pm list packages wechat`

To **remove** a package type:
`$ pm uninstall -k --user 0 to.be.removed`

In case you want to **reinstall** a package, run:
`$ cmd install-existing package.name.example`