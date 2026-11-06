# Terminal File Chooser (Yazi-based)

assets/example.gif

A universal terminal-powered file chooser for Linux desktops.

This project integrates **Yazi** with **XDG Desktop Portals**, allowing graphical applications to use a terminal file manager for opening and saving files.

Whether you're using GNOME, KDE Plasma, Hyprland, Sway, COSMIC, XFCE, or another desktop environment, you can keep file selection entirely within your terminal workflow.

## ✨ Features

- **Terminal-Powered** - Uses Yazi for fast, modern, and keyboard-driven file navigation.
- **Desktop Portal Integration** - Intercepts file chooser dialogs from graphical applications.
- **Distribution Agnostic** - Works on any Linux distribution that supports XDG Desktop Portals.
- **Desktop Environment Agnostic** - Compatible with GNOME, KDE Plasma, COSMIC, Hyprland, Sway, XFCE, Cinnamon, MATE, LXQt, and others.
- **Terminal Agnostic** - Works with WezTerm, Kitty, Ghostty, Alacritty, Foot, Konsole, Ptyxis, GNOME Terminal, Xfce Terminal, and many others.
- **Configurable** - Easily customize the terminal emulator, wrapper script, and default directories.

## 🏗 Architecture

```text
Application
      │
      ▼
XDG Desktop Portal
      │
      ▼
termfilechooser
      │
      ▼
Terminal Emulator
      │
      ▼
Yazi
```

## ⚙ Requirements

- Linux
- XDG Desktop Portals
- Yazi
- xdg-desktop-portal-termfilechooser
- Any supported terminal emulator

## 📦 Installation

### Arch Linux

```bash
yay -S xdg-desktop-portal-termfilechooser-hunkyburrito-git
```

### Other Linux Distributions

Install:

- Yazi
- xdg-desktop-portal
- xdg-desktop-portal-termfilechooser

using your distribution's package manager.

## 📂 Configuration

### File Chooser Configuration

Create:

```text
~/.config/xdg-desktop-portal-termfilechooser/config
```

Example:

```ini
[filechooser]
cmd=yazi-wrapper.sh
default_dir=$HOME
env=TERMCMD='wezterm -e'
open_mode=suggested
save_mode=last
```

#### Configuration Options

| Option | Description |
|----------|----------|
| `cmd` | Wrapper script used to launch Yazi |
| `default_dir` | Starting directory |
| `env` | Terminal emulator command |
| `open_mode` | Open dialog behavior |
| `save_mode` | Save dialog behavior |

Replace `wezterm` with your preferred terminal emulator if needed.

### Portal Configuration

Create:

```text
~/.config/xdg-desktop-portal/portals.conf
```

```ini
[preferred]
org.freedesktop.impl.portal.FileChooser=termfilechooser
```

## ✅ Compatibility

### Desktop Environments

- GNOME
- KDE Plasma
- COSMIC
- Hyprland
- Sway
- XFCE
- Cinnamon
- MATE
- LXQt
- Others supporting XDG Desktop Portals

### Terminal Emulators

- WezTerm
- Kitty
- Ghostty
- Alacritty
- Foot
- Konsole
- Ptyxis
- GNOME Terminal
- Xfce Terminal
- Many others

### Linux Distributions

- Arch Linux
- Fedora
- Ubuntu
- Debian
- openSUSE
- NixOS
- Gentoo
- And others

## 📸 Screenshot

_Add a screenshot or GIF here._

## 📄 License

Licensed under the MIT License.
