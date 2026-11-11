# Twitch Chat Window packages

Signed pacman packages for Twitch Chat Window on 64-bit CachyOS with KDE Plasma Wayland.

## Install on CachyOS

### Add the repository once

Download the public key and display its fingerprint.

```sh
curl -fL https://github.com/780APM/twitch-chat-window-packages/releases/latest/download/twitch-chat-window.asc -o twitch-chat-window.asc
gpg --show-keys --fingerprint twitch-chat-window.asc
```

Check that the fingerprint matches `12E83C4158AB44C6EEFA307ACB0167057F60AC5B`, then add and trust the key.

```sh
sudo pacman-key --add twitch-chat-window.asc
sudo pacman-key --lsign-key 12E83C4158AB44C6EEFA307ACB0167057F60AC5B
```

Add this section at the end of `/etc/pacman.conf`.

```ini
[twitch-chat-window]
SigLevel = PackageRequired DatabaseRequired TrustedOnly
Server = https://github.com/780APM/twitch-chat-window-packages/releases/latest/download
```

### Install the overlay

Refresh your package lists and install the app and its dependencies.

```sh
sudo pacman -Syu twitch-chat-window
```

Open **Twitch Chat Window** from the app menu. For the in-game unlock shortcut, bind `twitch-chat-window` to **Ctrl+Shift+F10** in Plasma’s **Keyboard → Shortcuts** settings.

Future app updates are included in regular `sudo pacman -Syu` upgrades.
