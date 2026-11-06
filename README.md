# Terminal File Chooser (Yazi-based)

A lightweight, terminal-powered file picker for Linux desktop environments that integrates a terminal file manager (`yazi`) with XDG Desktop Portals. This allows modern graphical applications to use your preferred terminal file manager for opening and saving files.

## 🚀 Features

* **Terminal-Powered:** Uses [Yazi](https://github.com/sxyazi/yazi) for fast, modern, and Vim-like file navigation.
* **XDG Desktop Portal Integration:** Seamlessly intercepts file chooser dialogs in modern apps (browsers, editors, etc.) and opens them via your terminal (`wezterm`).
* **Configurable:** Easily customize your preferred terminal emulator, wrapper script, and default directories.

---

## 📦 Installation

For Arch Linux users, install the required portal backend directly from the AUR using `yay`:

```bash
yay -S xdg-desktop-portal-termfilechooser-hunkyburrito-git
```

---

## 📂 File Locations & Setup

Place your configuration files in the following directory paths:

### 1. File Chooser Configuration
Save the `config` file to:  
`~/.config/xdg-desktop-portal-termfilechooser/config`

```ini
[filechooser]
cmd=yazi-wrapper.sh
default_dir=$HOME
env=TERMCMD='AnyTerminal -e'
open_mode=suggested
save_mode=last
```

* **`cmd`**: The wrapper script that launches the file manager (`yazi-wrapper.sh`).
* **`default_dir`**: The initial directory when the file chooser opens.
* **`env`**: Defines the terminal emulator used to run the file picker (`Any Terminal`).
* **`open_mode` / `save_mode`**: Controls how open and save dialogs handle file paths.
* Note: Replace "AnyTerminal" with the name of your preferred terminal emulator. Make sure it is installed and available in your system's PATH.
* For example:
* - WezTerm
- Kitty
- Ghostty
- Ptyxis
- Alacritty
- Foot
- Konsole
- And Other terminals

---

### 2. Portal Preference Configuration
Save the `portals.conf` file to:  
`~/.config/xdg-desktop-portal/portals.conf`

```ini
[preferred]
org.freedesktop.impl.portal.FileChooser=termfilechooser
```

---

## 🛠️ Requirements

* A Linux environment supporting XDG Desktop Portals.
* [Yazi](https://github.com/sxyazi/yazi) file manager.
* `wezterm` (or modify `env=TERMCMD` to use your preferred terminal like `alacritty`, `kitty`, etc.).
* `xdg-desktop-portal-termfilechooser` backend.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
