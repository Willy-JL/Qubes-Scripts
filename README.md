# qubes-scripts
Collection of custom scripts for Qubes OS

### Installation:
Just drop the scripts you want in `/usr/local/bin` on dom0 ([how to copy files to dom0](https://www.qubes-os.org/doc/how-to-copy-from-dom0/#copying-to-dom0))

### Explanation / Usage:
- `qubes-color-add/del`: **add and remove custom qube colors**; run the script with a color name and hexadecimal value like `qubes-color-add pink FABFD4`, then select it in a qube's settings page, remove with `qubes-color-del pink`
- `qubes-colorpick`: **pick a color from screen and copy to global clipboard**; run the script, select a color, paste into a qube of your choice
- `qubes-dom0-copy/move`: **import files to dom0 from other vms**; run the script, select the qube, then the files, and they will appear in the current directory on dom0 (and deleted on the source vm if moving)
- `qubes-flameshot`: **screenshot with flameshot and copy to qube clipboard**; run the script, make the screenshot, select target qube, paste to your heart's content
- `qubes-run-focused`: **run command in focused window's qube**; intended for use in keybinds, like opening a file manager in the focused window's qube
- `qubes-screenshare`: **quickly start a video companion screenshare session**; run the script, select destination qube, then source qube, do what you need, then stop screensharing with the tray icon
- `qubes-select-qube`: **show a prompt to select a qube**; intended for use in scripts and commands, all other scripts here rely on it

### Dependencies:
For the target qubes:

```bash
sudo dnf install \
    qubes-video-companion-receiver \
    xclip \
    yad
```

For dom0:
```bash
sudo qubes-dom0-update \
    flameshot \
    gpick \
    qubes-video-companion-dom0 \
    xdotool \
    xprop \
    yad
```

### Disclaimer:
You should be careful what you do with dom0, I won't be held responsible if anything gets compromised. Make sure you understand exactly what these scripts are doing (they are in fact quite simple) before you run them.
