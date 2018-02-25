# Gnome Display manager and login screen

GDM is admittedly quite fancy compared to alternatives, however, it is less
performant and does tend to fill up the system logs. The `lightdm` package
contains a simpler login manager with fewer dependencies, consider
switching to this.

To remove gdm:

```
sudo pacman -R gdm libgdm
```

Afterwards install lightdm:

```
sudo pacman -S lightdm
```

If you want a fancier GTK style login, consider the GTK greeter package as
well:

```
sudo pacman -S lightdm-gtk-greeter
```

Note that qt5 greeters are also available for lightdm, even if QT tends to
be a bit more heavy-weight than GTK, it is still a choice left for the
end-user.
