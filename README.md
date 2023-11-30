# archinstall

**Shell**: zsh  
**Window Manager**: Sway  
**Terminal**: Alacritty  
**Terminal Font**: JetBrainsMonoNerdFont  

### Installing paru
```sh
sudo pacman -S --needed base-devel git # includes tools for building
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si # builds and installs paru
paru # adds -Syu plags and updates the system
```

#### Install Packages:
```sh
paru -S zsh zip unzip z tldr tar ranger ripgrep python neofetch microsoft-edge-stable mpv man make lolcat ipv gcc fzf dunst cmatrix curl bluez-utils bluez blueman bat alacritty 1password
```

#### Installing nvim Config
* [kickstart github](https://github.com/nvim-lua/kickstart.nvim)
* [my kickstart fork](https://github.com/jacobneff/nvim) (clone this)
```sh
git clone https://github.com/jacobneff/nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim
```

---

### Install Fonts
* [How to install fonts video](https://www.youtube.com/watch?v=1RtLyPzbttA)
```sh
mkdir -p ~/.local/share/fonts
fc-cache -fv # force clear the cache
fc-list : family | grep "<font-name>" # list fonts family
fc-list : family style | grep "<font-name>" # list fonts family and style
fc-list : file | grep "<font-name>" # list fonts file path
```

###### Installing Special Fonts
```sh
paru -S noto-fonts # google fonts
paru -S nerd-fonts # nerd fonts 40 for JetBrainsMono Nerd Font
```

###### Changing Default Font
```sh
sudo nvim /etc/fonts/local.conf
```  

Font Previewer  
```sh
# Add dependencies: sxiv, imagemagick, xdotool, fzf
paru -S sxiv imagemagick xdotool
paru -S fontpreview # better font previewer
```
* [fontpreview github](https://github.com/sdushantha/fontpreview)

---

##### How to change brightness
```sh
man brightnessctl
```
