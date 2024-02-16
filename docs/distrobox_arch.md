## how to install gmanka's neovim and neovide config in arch distrobox

### navigation

- [main docs page](https://github.com/gmankab/nvgmanka)
- arch distrobox guide, you are here
- [neovim config lua repo](https://github.com/gmankab/nvim_config)

### configuring distrobox

1. [install distrobox](https://github.com/89luca89/distrobox#installation)
2. reboot
3. create and enter arch distrobox:

```shell
distrobox create -i docker.io/archlinux/archlinux:latest arch
distrobox enter arch
```

### install neovim and config

```shell
sudo pacman -Syu --noconfirm neovim git wl-clipboard gcc npm ripgrep fd
git clone --depth 1 https://github.com/gmankab/nvim_config ~/.config/nvim
```

### install jetbrains mono font
```shell
curl -L github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/JetBrainsMono.tar.xz -o /tmp/jbm/jbm.tar.xz --create-dirs
tar -xf /tmp/jbm/jbm.tar.xz -C /tmp/jbm
mkdir -p ~/.local/share/fonts
cp /tmp/jbm/JetBrainsMonoNerdFont-Regular.ttf ~/.local/share/fonts/jbm.ttf.ttf
```

### install neovide and config

```shell
sudo pacman -Syu --noconfirm libxkbcommon neovide
curl -L raw.githubusercontent.com/gmankab/nvgmanka/main/.config/neovide/config.toml -o ~/.config/neovide/config.toml --create-dirs
```

### export app outside of distrobox
```shell
distrobox-export --app neovide
```
