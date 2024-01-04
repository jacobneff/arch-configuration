# Arch Configuration

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
paru -S 1password alacritty azote bat blueman bluez bluez-utils curl cmake cmatrix dunst fuse fzf gcc ipv libinput logiops lolcat make man mpv microsoft-edge-stable neofetch powertop python ripgrep ranger solaar spotify-tui spotifyd tldr tar unzip usbutils z zellij zsh zip
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

#### Build Neovim From Source

```sh
# install dependencies
sudo pacman -S base-devel cmake unzip ninja tree-sitter curl
```

```sh
git clone https://github.com/neovim/neovim.git
```

```sh
cd neovim
```

```sh
make CMAKE_BUILD_TYPE=RelWithDebInfo
```

```sh
sudo make install
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

### Fixing Bluetooth in Dual Boot

* (AUR)[https://wiki.archlinux.org/title/bluetooth#Dual_boot_pairing]
* (BT-dualboot repo)[https://github.com/x2es/bt-dualboot]

```sh
paru -S python3
paru -S python-pip
sudo pip install bt-dualboot
```

---

### Logitech Mouse Configuration

* `logid` (onfiguration with a file)
* `solaar` (configuration with a gui)

---

### sddm Theme

```sh
paru -S sddm-theme-tokyo-night
```

##### Edit the sddm config file

* `sudo nvim /etc/sddm.conf`

```
[Theme]
Current=tokyo-night-sddm
```

* [theme repo](https://github.com/rototrash/tokyo-night-sddm)

---

### Power Management
* `sudo nvim /etc/systemd/system/powertop.service`

```sh
[Unit]
Description=Powertop tunings

[Service]
Type=oneshot
RemainAfterExit=yes
ExecStart=/usr/bin/powertop --auto-tune

[Install]
WantedBy=multi-user.target
```

##### Enable Service
* `sudo systemctl enable powertop.service`

##### Calibrate Powertop
* `sudo powertop --calibrate`

---

### Wallpaper Config

* using `azote` and running it inside sway wm: `exec ~/.azotebg`
* run `azote` in terminal to pick the wallpaper

---

### Change brightness
```sh
man brightnessctl
```
