## how to install gmanka's neovim and neovide config in fedora distrobox

### configuring distrobox

1. [install distrobox](https://github.com/89luca89/distrobox#installation)
2. reboot
3. create and enter arch distrobox:

```shell
distrobox create -i fedora:39 fedora
distrobox enter fedora
```

### install neovim and config

```shell
sudo dnf upgrade -y
sudo dnf install -y neovim git wl-clipboard gcc npm ripgrep fd-find
git clone --depth 1 https://github.com/gmankab/nvim_config ~/.config/nvim
```

### install neovide and config

```shell
sudo dnf upgrade -y
sudo dnf install -y libxkbcommon libxkbcommon-x11 fontconfig libwayland-egl libglvnd-egl
curl -L github.com/neovide/neovide/releases/latest/download/neovide-linux-x86_64.tar.gz -o /tmp/neovide.tar.gz
tar -xzf /tmp/neovide.tar.gz -C /tmp
chmod +x /tmp/neovide
sudo cp /tmp/neovide /bin/neovide
curl -L github.com/gmankab/nvgmanka/blob/main/.config/neovide/config.toml -o ~/.config/neovide/config.toml --create-dirs
```

