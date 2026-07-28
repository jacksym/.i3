# The i3 Configuration and Download Protocol
### (The Fedora i3 Spin Branch)

## Base Packages

```
sudo dnf install vim vim-X11
                 xterm xscreensaver
                 xinput
                 git
                 tar unzip
                 llvm clang clang-devel
                 zathura
                 feh
```

## Git & GitHub CLI Install and Configuration
git config
```
git config --global user.name "Jack"
git config --global user.email "jacksymonds.js@gmail.com"

```

installing and configuring Github
```
sudo dnf install dnf5-plugins
sudo dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
```
Auth Login:
```
gh auth login
```



## Sound
We'll be using PipeWire -- pending on whether that's compatible with REAPER

Just in case: (troubleshooting [doc](https://docs.fedoraproject.org/en-US/quick-docs/how-to-troubleshoot-sound-problems/)
fixed this early
```
sudo update-pciids
sudo dnf install --allowerasing pipewire-pulseaudio


```

## Uninstalls

```
sudo dnf remove mousepad
sudo dnf remove Thunar
rm -rf ~/.config/Thunar ~/.config/xfce4
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
GIMP \& Inkscape
</strong> </summary>
Nice, they're in dnf

```
sudo dnf install gimp inkscape
```

</details>

### Manual Installations

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
./install-reaper.sh
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
- sshing to jackserver
- get volume working
- default everything to floating -- prepare for windows like workflow
- ssh instructions
- blender instructions
