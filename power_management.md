# Power management and control

Most power features are now controlled directly from the kernel, so
individual daemons that manage batteries are not strictly necessary; unless
the given computer has a more complex system of power; e.g. multiple levels
of UPS subsystems.

Ergo, feel free to simply remove the systemd-ified daemon in question:

```
sudo pacman -R upower xfce4-power-manager
```
