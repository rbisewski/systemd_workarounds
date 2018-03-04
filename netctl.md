# Network Control Daemon

Systemd contains a network management utility by the name of `netctl`.
Since there are already a number of POSIX-compat GNU utils present in every
Linux distro, it is not needed and can be removed like so:

```
sudo pacman -R netctl
```
