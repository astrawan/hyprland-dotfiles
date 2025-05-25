# Dotfiles for Hyprland WM

## Fedora Silverblue

### Hyprland Repo from COPR

```sh
cat > /etc/yum.repos.d/solopasha-hyprland-fedora.repo <<EOL
[copr:copr.fedorainfracloud.org:solopasha:hyprland]
name=Copr repo for hyprland owned by solopasha
baseurl=https://download.copr.fedorainfracloud.org/results/solopasha/hyprland/fedora-\$releasever-\$basearch/
type=rpm-md
skip_if_unavailable=True
gpgcheck=1
gpgkey=https://download.copr.fedorainfracloud.org/results/solopasha/hyprland/pubkey.gpg
repo_gpgcheck=0
enabled=1
enabled_metadata=1
EOL
```

### Install Hyprland and Dependencies

```sh
rpm-ostree install \
  blueman \
  distrobox \
  fuzzel \
  hypridle \
  hyprland \
  hyprlock \
  hyprshot \
  mako \
  network-manager-applet \
  stow \
  udiskie \
  usbguard-notifier \
  usbguard-tools waybar

```

### Install Dotfile Symlinks

```sh
stow --verbose=3 --target="$HOME" --adopt .
```

### Uninstall Dotfile Symlinks

```sh
stow --verbose=3 --target="$HOME" -D .
```
