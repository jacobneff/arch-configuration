# archinstall

**Shell**: zsh  
**Window Manager**: Sway  
**Terminal**: Alacritty  
**Terminal Font**: JetBrainsMonoNerdFont  

---

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
paru -S 1password alacritty bat blueman bluez bluez-utils curl cmake cmatrix dunst fuse fzf gcc ipv logiops lolcat make man mpv microsoft-edge-stable neofetch python ripgrep ranger solaar tldr tar unzip z zsh zip
```

---

### Configure oh-my-zsh
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
* [oh-my-zsh](https://ohmyz.sh/)

---

### Configuring Neovim

#### Install Neovim Nightly Release

```sh
wget https://github.com/neovim/neovim/releases/download/nightly/nvim.appimage
chmod u+x nvim.appimage && ./nvim.appimage
mv nvim.appimage nvim && sudo mv nvim /usr/bin/
```

##### If system does not have FUSE
```sh
./nvim.appimage --appimage-extract
./squashfs-root/usr/bin/nvim
```

#### Neovim Config
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
curl <url-to-font>
unzip <font>
mv <font> ~/.local/share/fonts
fc-cache -fv # force clear the cache
```

##### Installing Special Fonts
```sh
paru -S noto-fonts # google fonts
paru -S nerd-fonts # nerd fonts 40 for JetBrainsMono Nerd Font
```

##### Changing Default Font
```sh
sudo nvim /etc/fonts/local.conf
```  

#### View Fonts

```sh
fc-list : family | grep "<font-name>" # list fonts family
fc-list : family style | grep "<font-name>" # list fonts family and style
fc-list : file | grep "<font-name>" # list fonts file path
```

##### Font Previewer  
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
