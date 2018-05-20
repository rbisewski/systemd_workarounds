# Miscellaneous packages

Numerous smaller systemd services and daemons exist for niche applications,
such as color profiling or PC-MCIA management, and are not strictly
necessary for the functioning of a normal Linux machine. They can be
removed like so: 

```
sudo pacman -R pcmciautils

sudo pacman -Rdd colord colord-gtk
```

At this time `flatpak` is not popular and has limited use, feel free to
remove it from the system.

```
sudo pacman -R flatpak
```

If you are not using a Wacom tablet or touchscreen, it can be removed like
so:

```
sudo pacman -Rdd libwacom
```
