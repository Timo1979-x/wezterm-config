## What is this
My wezterm config. inspired by [wezterm config by Kevin Silvester](https://github.com/KevinSilvester/wezterm-config)

Modified copy of Kevin's config included here for my reference in `_KevinSilverster` directory.

## Requirements
- [IosevkaTerm Nerd Font Mono](https://www.nerdfonts.com/font-downloads) ([direct link](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.3.0/IosevkaTerm.zip))

## Usage
### Linux
```bash
git clone git@github.com:Timo1979-x/wezterm-config.git %USERPROFILE%\.config\wezterm
```
### Windows
```
git clone git@github.com:Timo1979-x/wezterm-config.git "%USERPROFILE%\.config\wezterm"
```

### getting help
You can display current keyboard shortcuts with descriptios splitted by category. Press `F12` to open debug overlay, then call `_keys()` function.


## Improvements
### quake-style in Linux
Needed script [tdrop](https://github.com/noctuid/tdrop).

Install tdrop prerequisites:
```
apt install bash gawk grep procps x11-utils xdotool -y
```
download tdrop script from its github repo and place it into `/usr/local/bin/tdrop`.

In your window manager create global keybinding (i.e. "Ctrl + ~") for this command:
```
tdrop -w 100% -h 100% wezterm
```

### quake-style in Windows
You'll need [Autohotkey v2](https://www.autohotkey.com/v2/)

Create file `wezterm.ahk` somewhere with [this content](./docs/ahk.md)

Make it autostart with Windows. for example place shortcut in the "startup" folder with this command:
```
"%LOCALAppData%\Microsoft\WindowsApps\AutoHotkey.exe" d:\utils\scripts\wezterm.ahk
```
You can reach startup folder with `explorer shell:startup` command.

After start, AHK will show wezterm icon in windows system tray. There is small context menu associated with this icon.

My default keybinding for emerging wezterm is "Ctrl + ~". You can change it in `wezterm.ahk` file.

## Plans
- make keyboard shortcut to print my keybindings directly into current pane (in human-friendly format)

## Useful wezterm commands
### show keybindings
`wezterm show-keys`

## default wezterm config for my reference
[here](./docs/default-config.md)

## default wezterm keybindings for my reference
[here](./docs/default-keys.md)
