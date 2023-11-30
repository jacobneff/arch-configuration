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

### Install Initial Packages:
```sh
paru -S zsh zip unzip z tldr tar ranger python neovim neofetch mpv man-db make lolcat ipv gcc fzf dunst cgra cmatrix curl bluez-utils bluez blueman bat alacritty 1password
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
paru -S imagemagick # font previewer
paru -S fontpreview # better font previewer
```
* [fontpreview github](https://github.com/sdushantha/fontpreview)

---

##### How to change brightness
```sh
man brightnessctl
```
