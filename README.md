# dotfiles

My personal dotfiles for a [CachyOS](https://cachyos.org/) setup running the [niri](https://github.com/YaLTeR/niri) Wayland compositor.

## Screenshots

![Desktop with fastfetch](images/2.jpg)

![Wallcards](images/1.jpg)

![Editor](images/3.jpg)

## Setup

| Component        | Tool                                               |
| ---------------- | -------------------------------------------------- |
| OS               | CachyOS x86_64                                     |
| Kernel           | Linux 7.0.9-1-cachyos                              |
| WM               | [niri](https://github.com/YaLTeR/niri) 26.04       |
| Shell            | [noctalia-shell](https://github.com/noctalia-dev/noctalia-shell) via quickshell |
| Terminal         | [Alacritty](https://alacritty.org/) 0.17           |
| CLI Shell        | [fish](https://fishshell.com/)                     |
| Editor           | [Zed](https://zed.dev/)                            |
| Clipboard UI     | [fuzzel](https://codeberg.org/dnkl/fuzzel) + [cliphist](https://github.com/sentriz/cliphist) |
| Fetch            | [fastfetch](https://github.com/fastfetch-cli/fastfetch) |

## Dependencies

Core packages used by the configs:

```sh
sudo pacman -S --needed alacritty fish fuzzel fastfetch cliphist wl-clipboard nautilus libnotify pavucontrol gpu-screen-recorder psmisc capitaine-cursors adwaita-fonts cachyos-fish-config
```

Applications referenced directly from niri keybinds:

```sh
sudo pacman -S google-chrome zed telegram-desktop discord amneziavpn-bin
```

Noctalia extras referenced by settings/templates:

```sh
sudo pacman -S btop cava spicetify-bin
```

Noctalia plugins enabled in this config:

- `wallcards`
- `polkit-agent`

Notes:

- Noctalia shell/qs are expected to come from the CachyOS niri/noctalia system package or profile.
- `pwvucontrol` is optional; the volume widget falls back to `pavucontrol`.
- The system monitor button tries multiple apps, including `resources`, `missioncenter`, and `gnome-system-monitor`; install whichever one you prefer.
- Personal app binds can be swapped in [niri/cfg/keybinds.kdl](niri/cfg/keybinds.kdl).

## Structure

```
dotfiles/
├── alacritty/      # Terminal config and Noctalia theme
├── fastfetch/      # Fetch tool config
├── fish/           # Shell config
├── fuzzel/         # Launcher/clipboard UI config
├── niri/           # Window manager config
├── noctalia/       # Noctalia settings and plugin config
├── zed/            # Editor themes
└── images/         # Screenshots
```

## Usage

Clone the repo and symlink configs to their respective locations:

```sh
git clone https://github.com/anxi0uz/dotfiles ~/.dotfiles
```

Then symlink individual configs as needed, for example:

```sh
ln -s ~/.dotfiles/alacritty ~/.config/alacritty
ln -s ~/.dotfiles/fish ~/.config/fish
ln -s ~/.dotfiles/niri ~/.config/niri
ln -s ~/.dotfiles/fuzzel ~/.config/fuzzel
ln -s ~/.dotfiles/fastfetch ~/.config/fastfetch
ln -s ~/.dotfiles/noctalia ~/.config/noctalia
ln -s ~/.dotfiles/zed/themes ~/.config/zed/themes
```
