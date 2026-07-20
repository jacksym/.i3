# The i3 Configuration and Download Protocol
### (The Fedora i3 Spin Branch)

## Base Packages

```
sudo dnf install vim vim-X11
                 git
                 zathura
```

<details>
<summary>
### Chrome
</summary>
```
sudo dnf install fedora-workstation-repositories
sudo dnf config-manager setopt google-chrome.enabled=1
sudo dnf install google-chrome-stable
```
</details>

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
Auth Login:
```
gh auth login
```

## TODO:
- get volume working
- default everything to floating -- prepare for windows like workflow
- ssh instructions
- blender instructions

