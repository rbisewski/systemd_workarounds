# Systemd Workarounds

A compilation of ideas concerning systemd services and their alternatives.
Specifically this repo contains a number of ideas to reduce the number of
packages needed for a given Archlinux system. Ideally, the goal is to
minimize the dependency on systemd, with the objective of removing bloat.

## Current workarounds available

* Pulseaudio
* GDM / systemd login
* NetCtl
* Power Management
* AccountService
* Various miscellaneous Linux packages associated with systemd

## About

In theory the author has no major objection to systemd, as in all fairness
it did attempt to manage the chaos of the SysV era init scripts and
daemons. Recently, however, systemd has become a bit more bloated than the
typical Linux user needs and is causing slowness and odd hangups in the
system should a service be configured imperfectly or nonstandardly.

Ergo, reducing the level of dependencies on systemd is essential to a more
usable modern Linux experience.
