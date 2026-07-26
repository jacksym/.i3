#The i3 Configuration and Download Protocol
(The Fedora i3 Spin Branch)

## Base Packages

```
sudo dnf install vim vim-X11
                 git
                 zathura
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

### Chrome
```
sudo dnf install fedora-workstation-repositories
sudo dnf config-manager setopt google-chrome.enabled=1
sudo dnf install google-chrome-stable
```

### Spotify
```
sudo dnf install \
 https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install lpf-spotify-client
lpf update
```

### TripleA (for fun)
```
sudo dnf install java-latest-openjdk
```
Download Executable from [this link](https://triplea-game.org/download/)
```
chmod +x ./TripleA_*unix.sh && ./TripleA_*unix.sh

```

### GitHub CLI Install and Configuration
To install:
```
sudo dnf install dnf5-plugins
sudo dnf config-manager addrepo --from-repofile=https://cli.github.com/packages/rpm/gh-cli.repo
sudo dnf install gh
```
To upgrade:
```
sudo dnf update gh
```
Auth Login:
```
gh auth login
```

## TODO:
- get volume working
- default everything to floating -- prepare for windows like workflow
