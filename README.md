Arch
====

Collection of points on installing / using arch-linux

### Networking

Network failures are often due to 2 or more Network Managers running at the same time. To enable WiFi with wifi-menu I had to do

	ip link set device down

And then wifi-menu could start connection with the router.
Also if dhcpcd is running that could be interfering with another manager.

#### NetworkManager

Enable network manager

    systemctl enable NetworkManager

Start network manager

    systemctl start NetworkManager

List nearby networks

    nmcli device wifi list

Connect to a nearby network

    nmcli device wifi connect <WifiName> password <SSID_password>

### Packages

Important packages for all kinds of stuff

* base-devel ( includes make and friends )


#### AUR

For some dependencies, unofficial packages, older releases etc, you will need to access packages on
[AUR](https://aur.archlinux.org/). There are helpers for this, see:

* [Yay](https://github.com/Jguer/yay)

Resources

* [How to Install Yay AUR Helper in Arch Linux and Manjaro](https://www.tecmint.com/install-yay-aur-helper-in-arch-linux-and-manjaro/)
