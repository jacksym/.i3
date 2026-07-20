# The i3 Configuration and Download Protocol
### (The Fedora i3 Spin Branch)

## Base Packages

```
sudo dnf install vim vim-X11
                 git
                 zathura
```

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
### GitHub CLI Install and Configuration
</strong> </summary>

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
</details>

## TODO:
- get volume working
- default everything to floating -- prepare for windows like workflow
- ssh instructions
- blender instructions

