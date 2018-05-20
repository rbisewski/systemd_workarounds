# Pulse Audio

Unfortunately, for modern usability on many aspects of Linux desktops,
pulseaudio is needed to make it easy to manage various types of audio
devices.

That said, for a minimalist system, the ALSA libs are sufficient for
most applications. Ergo the pulseaudio packages themselves can be removed
as follows:

```
sudo pacman -R pulseaudio pulseaudio-alsa pulseaudio-bluetooth pulseaudio-equalizer pulseaudio-jack rtkit
```

However, on some systems you may need to select the given sound card that
is the default. Currently there are two methods:

a) Select a default sound card for a given user, add the following file to
   the user's home directory:

```
touch ~/.asoundrc
```

b) Or to enforce systemwide sound card, create the following file:

```
sudo touch /etc/asound.conf
```

Once this is done, check which sound cards are currently detected by the
kernel:

```
aplay -a
```

Afterwards a list of potentially usable sound cards on the system will be
printed to the console. It should look something like this:

```
**** List of PLAYBACK Hardware Devices ****
card 0: HDMI [HDA ATI HDMI], device 3: HDMI 0 [HDMI 0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: HDMI [HDA ATI HDMI], device 7: HDMI 1 [HDMI 1]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: HDMI [HDA ATI HDMI], device 8: HDMI 2 [HDMI 2]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: HDMI [HDA ATI HDMI], device 9: HDMI 3 [HDMI 3]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: HDMI [HDA ATI HDMI], device 10: HDMI 4 [HDMI 4]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: HDMI [HDA ATI HDMI], device 11: HDMI 5 [HDMI 5]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: Generic [HD-Audio Generic], device 0: ALC887-VD Analog [ALC887-VD Analog]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: Generic [HD-Audio Generic], device 1: ALC887-VD Digital [ALC887-VD Digital]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
```

Upon doing either-or, then add the following lines:

```
pcm.!default {
    type hw
    card 1
}

ctl.!default {
    type hw
    card 1
}
```

Where `1` is the sound card you have selected. In this case, the generic
`ALC887-VD` audio card will become the default sound card on the system.
