# archinstall

**Shell**: zsh  
**Window Manager**: Sway  
**Terminal**: Alacritty  
**Terminal Font**: JetBrainsMonoNerdFont  

#### Installing paru
```zsh
sudo pacman -S --needed base-devel git # includes tools for building
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si # builds and installs paru
paru # adds -Syu plags and updates the system
```

#### Install Initial Packages:
```sh
paru -S zsh zip unzip z tldr tar python neovim neofetch mpv man-db make lolcat ipv gcc fzf dunst cgra cmatrix curl bluez-utils bluez blueman bat alacritty 1password
```

##### How to change brightness
```sh
man brightnessctl
```
