## how to install gmanka's neovim and neovide config in arch distrobox

### navigation

- [main docs page](https://github.com/gmankab/nvgmanka)
- arch distrobox guide, recommended, you are here
- [fedora distrobox guide](https://github.com/gmankab/nvgmanka/blob/main/docs/distrobox_fedora.md)
- [neovim config lua repo](https://github.com/gmankab/nvim_config)

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
sudo pacman -Syu --noconfim neovim git wl-clipboard gcc npm ripgrep fd
git clone --depth 1 https://github.com/gmankab/nvim_config ~/.config/nvim
```

### install neovide and config

```shell
sudo pacman -Syu --noconfim libxkbcommon neovide
curl -L github.com/gmankab/nvgmanka/blob/main/.config/neovide/config.toml -o ~/.config/neovide/config.toml --create-dirs
```

