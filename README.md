# sysconfig
System configuration files

# Pulseaudio
Setup for local network access to pulseaudio server.

Packages needed on server:
- Debian: `apt-get install pulseaudio pulseaudio-module-zeroconf alsa-utils avahi-daemon dbus-x11`

Packages needed on client:
- Arch Linux: `pacman -S pulseaudio pulseaudio-alsa pulseaudio-zeroconf pavucontrol paprefs`

1. Copy files in etc/pulse/ to /etc/pulse/
2. Copy pulseaudio.service to /etc/systemd/system/
3. Enable pulseaudio service with `systemctl enable pulseaudio.service`
4. Start pulseaudio service with `systemctl start pulseaudio.service`
5. Open `paprefs` and check `Network Access -> Make discoverable PulseAudio network sound devices available locally`
6. For RTP streaming, check `Multicast/RTP -> Enable Multicast RTP sender -> Create separate audio device for Multicast/RTP`
7. Open `pavucontrol`. You should see remote audio sinks in `Output Devices` tab
