# zsh
Install zsh:
```
sudo apt install zsh-autosuggestions zsh-syntax-highlighting zsh
```
Install Oh my ZSH
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Install plugin
- autosuggesions plugin
```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

- zsh-syntax-highlighting plugin
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

- zsh-fast-syntax-highlighting plugin
```

git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```
- zsh-autocomplete plugin
```
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```
File .zshrc
```
alias python=python3
chekcip(){
	curl "ipinfo.io/$1?token=e44bf8dc3836de"
}
alias checkip=checkip
```

# Docker
Install docker engine using apt repository
1. Setup Docker's apt repository
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
2. Install Docker packages
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
3. Add user to docker group
```
 sudo usermod -aG docker $USER
```

# Fcitx5
```
sudo apt install fcitx5 fcitx5-unikey
```
Add below lines to .bashrc
```

export GTK_IM_MODULE=fcitx5
export XMODIFIERS=@im=fcitx5 
export QT_IM_MODULE=fcitx5
```

# Kerio-control (deb)
```
ExecStartPost=/bin/sh -c "cat /var/log/kerio-kvc/debug.log | grep MAC | tail -1 | tr - : |rev|cut -d' '  -f 1|rev| xargs -I {} ip link set kvnet addr {}"
```
# Scrcpy
1. Install dependencies
```
sudo apt install ffmpeg libsdl2-2.0-0 adb wget \
                 gcc git pkg-config meson ninja-build libsdl2-dev \
                 libavcodec-dev libavdevice-dev libavformat-dev libavutil-dev \
                 libswresample-dev libusb-1.0-0 libusb-1.0-0-dev
```
2. Install scrcpy
```
git clone https://github.com/Genymobile/scrcpy
cd scrcpy
./install_release.sh
```
3. Update scrcpy
```
git pull
./install_release.sh
```
# Additional ultities
1. Using apt to install
- nginx-extras/stable 
- btop 
- neofetch
- wireshark
- nmap
- vlc media players
- thunderbird

2. Download and install with dpkg
- Terminus (deb)
- Tabby
- Obsidian
- Chrome
- Microsoft Edge
- VS code
- Telegram

1. Install by script
- Burpsuite

# Metaploit framework
# OBS
# WPS
Fix isssues with front
1. Download the fronts as zip file at: [https://github.com/udoyen/wps-fonts](https://github.com/udoyen/wps-fonts) 
2. Create folder to store ttf
```
sudo mkdir /usr/share/fonts/kingsoft
sudo chown -R $USER:$USER /usr/share/fonts/kingsoft
sudo chmod -R o+rw,g+rw /usr/share/fonts/kingsoft
```
3. Copy all ttf file to /usr/share/fonts/kingsoft