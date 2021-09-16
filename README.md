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

### System time

To sync date/time with time servers, install ntp

    pacman -S ntp

Enable ntp service so it starts on startup/reset

    systemctl enable ntpd.service

Start the service

    systemctl start ntpd.service

### Packages

Important packages for all kinds of stuff

* base-devel ( includes make and friends )


#### AUR

For some dependencies, unofficial packages, older releases etc, you will need to access packages on
[AUR](https://aur.archlinux.org/). There are helpers for this, see:

* [Yay](https://github.com/Jguer/yay)

Resources

* [How to Install Yay AUR Helper in Arch Linux and Manjaro](https://www.tecmint.com/install-yay-aur-helper-in-arch-linux-and-manjaro/)

### Other

#### Clipboard

For some reason I had to add the following line to my .bashrc to be able to
work with "y" in vim so it copies the text to the system clipboard

    export DISPLAY=:1

### Language

    sudo pacman -S noto-fonts-cjk noto-fonts-emoji noto-fonts
