Pulseaudio
===

pavucontrol is a good visual interface for seeing all ongoing streams.

    pacman -S pavucontrol

### Issues

Bluetooth related issue that came up

    [pulseaudio] bluez5-util.c: GetManagedObjects() failed: org.freedesktop.systemd1.NoSuchUnit: Unit dbus-org.bluez.service not found.


[Solution](https://bbs.archlinux.org/viewtopic.php?id=155714)


### Restarting pulseaudio

Sound seems to drop out randomly e.g. after plugging in headphones.
In this case, alsamixer shows that Master is not muted and pavucontrol shows
a signal coming from the application. Temporary fix for this is to simply
restart PulseAudio

    pulseaudio -k 
    pulseaudio --start

