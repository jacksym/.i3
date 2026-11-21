# The Sway Configuration and Download Protocol
### (The Debian Sway Branch)
## Initial (for sway to work)

```
sudo apt install sway swaybg swaylock swayidle waybar xwayland rofi alacritty wl-clipboard
```

## Base Packages

```
sudo dnf install vim vim-gtk3
                 gurl gnupg
                 git
                 tar unzip
                 llvm clang clang-devel
                 zathura
                 texliive-full
                 fonts-recommended
                 fonts-font-awesome
                 gnome-keyring
                 nm-applet
```

## Git & GitHub CLI Install and Configuration
git config
```
git config --global user.name "Jack"
git config --global user.email "jacksymonds.js@gmail.com"
```

installing and configuring Github
```
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```
Auth Login:
```
gh auth login
```



## Sound
We'll be using PipeWire -- pending on whether that's compatible with REAPER

```
sudo apt install pipewire-audio
systemctl --user restart wireplumber pipewire pipewire-pulse

```

## dnf Installs

<details>
<summary> <strong>
Chrome
</strong> </summary>

```
sudo dnf install fedora-workstation-repositories
sudo dnf config-manager setopt google-chrome.enabled=1
sudo dnf install google-chrome-stable
```

</details>

<details>
<summary> <strong>
Spotify
</strong> </summary>

```
sudo dnf install \
 https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install lpf-spotify-client
lpf update
```
</details>
<details>
<summary> <strong>
Steam
</strong> </summary>

Get the external repository
```
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm -y
sudo dnf config-manager setopt fedora-cisco-openh264.enabled=1
```
Install:
```
sudo dnf install steam -y
```

</details>

<details>
<summary> <strong>
Discord
</strong> </summary>

```
sudo dnf install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
sudo dnf update
sudo dnf install discord
```

</details>

<details>
<summary> <strong>
GIMP & Inkscape
</strong> </summary>
Nice, they're in dnf

```
sudo dnf install gimp inkscape
```

</details>

### Manual Installations

<details>
<summary> <strong>
LogiOptions
</strong> </summary>

Download .rpm from [this link](https://openlogi.org/en/docs/getting-started/installation)

```
sudo rpm -i openlogi-*.rpm

systemctl --user enable --now openlogi-agent.service
```

</details>


<details>
<summary> <strong>
TripleA (for fun)
</strong> </summary>

```
sudo dnf install java-latest-openjdk
```
Download Executable from [this link](https://triplea-game.org/download/)
```
chmod +x ./TripleA_*unix.sh && ./TripleA_*unix.sh
```

</details>

<details>
<summary> <strong>
REAPER
</strong> </summary>

Install dependencies
```
sudo dnf install libc6 libstdc++ libgdk-3 libmp3lame
```

Download tar file from [this link](https://www.reaper.fm/download.php)

```
tar -xf ...
./install-reaper.sh
```
With the following options:
```
[i] install reaper
[3] into /opt
²±
```

</details>


<details>
<summary> <strong>
Blender
</strong> </summary>


Download tar file from [this link](https://www.blender.org/download/release/)

```
sudo tar -xf ~/Downloads/Blender...
```

</details>

<details>
<summary> <strong>
Godot (and .NET)
</strong> </summary>

Install .NET dependencies
```
glibc
libcc
ca-cacertificates
openssl-libs
libstdc++
libicu
tzdata
krb5-libs
(zlib)
```

Install  .NET
```
sudo dnf install dotnet-sdk-10.0
sudo dnf install aspnetcore-runtime-10.0
sudo dnf install dotnet-runtime-10.0
```

Download zip file from [this link](https://godotengine.org/download/linux/)

```
sudo -unzip ~/Downloads/Godot... -d /opt
```

</details>




## SSH Configuration
Install SSH and configure...

make the key
```
ssh-keygen -t ed25519 -a 100 <loc>
```
move the contents of the public key to `/home/jack/.ssh/<allowed-keys>`

Add this to `~/.ssh/config`
```
Host jackserver
    HostName ajs-online.org
    User jack
    Port 22222
    IdentityFile <loc>
```


## TODO:
- SWAY Completion
- swaybar completion
    - bar colors
- window colors
- system fonts that aren't bad
- rofi configuration
    - rofi as a file manager?
- clipboard
- alacritty configuration (clipboard)
- storage inspector
- i3 mastery
    - default floating
