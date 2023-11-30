# archinstall


**Shell**: zsh
**Window Manager**: Sway
**Terminal**: Alacritty
**Terminal Font**: JetBrainsMonoNerdFont

#### Initial Packages:
```sh
sudo pacman -S zsh zip unzip z tldr tar python neovim neofetch mpv man-db make lolcat ipv gcc fzf dunst cgra cmatrix curl bluez-utils bluez blueman bat alacritty 1password
```

#### Installing yay
```sh
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
sudo pacman -S base-devel
makepkg -si
```
