<img width="1300" height="300" alt="logo" src="https://github.com/user-attachments/assets/18a14fa4-ebef-4780-a661-e86016124134" />


# TurboWM (tbwm)

a dynamic tiling wayland compositor with shitty scheme scripting

> La documentación canónica de este fork es
> [`Gagedito/tbwm-fixes`](https://github.com/Gagedito/tbwm-fixes) (README y
> `docs/`); este README es solo el resumen rápido.

features:
- scheme configuration: lots configurable at runtime via ~/.config/tbwm/config.scm (not that good tho)
- launcher: you can press super+d for application launcher. i should probably make it a seperate app but like uhuhuj
- scheme repl: (super+shift+;)
- network menu (super+n): wifi + bluetooth with password prompt and in-menu pairing passkey dialog (see tbwm-network)
- screen capture with grim+slurp built into the default config (Print / S-Print)
- wallpaper: layer-shell friendly. image with swaybg or dynamic wallpapers with waywallen via tbwm-wallpaper (degrades to default background if waywallen isn't installed)

## installation

just run:
```bash
git clone https://github.com/Gagedito/tbwm
cd tbwm
./install.sh
```

the script will:
- detect your distro and install dependencies
- build wlroots 0.19 from source if your distro's version is too old (looking at you debian)
- build and install tbwm
- set up the session file so it shows up in your display manager

then log out and select "TurboWM" from your display manager. or run `tbwm` from a tty

### manual build (if you hate convenience)

dependencies:
- wlroots 0.19+
- wayland, wayland-protocols
- libinput, xkbcommon
- freetype2, pixman
- dbus (system tray)
- libxcb, xcb-icccm (for XWayland)

```bash
git clone https://github.com/Gagedito/tbwm
cd tbwm
make
sudo make install
```

## configuration

configuration is done via ~/.config/tbwm/config.scm

check out docs/configuration.md for all the options or just press super+\` to open the repl and figure it out yourself
