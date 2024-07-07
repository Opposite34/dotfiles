# My dotfiles

## Important
This is not my full dotfiles. The reason is I based my kitty and hyprland from the default config and currently do not have time to properly organize them. However, they are mostly environment-specific anyway (nvidia stuffs, localized fontmapping, etc). Most of stuffs here should get you very close to my config.

## General Details
- Most of the colorschemes are based on the wallpaper or [catppuccin's palette](https://catppuccin.com/palette) (namely, catppuccin mocha)

- List of the general programs I use:
    * WM: Hyprland 
    * Status bar: EWW
    * Notification: mako
    * Application launcher: tofi
    * Shell: zsh
    * Terminal: kitty 
    * Terminal prompt: starship (config based on the Tokyo Night preset with changes in palette)
    * Editor: neovim
    * Image viewer: imv
    * Media player: mpv and termusic
    * File explorer: vifm

## Dependencies
1. A windows manager (I use Hyprland, but pretty sure xorg stuffs should work)
2. Font - I use Iosevka without patch as I have a separate NerdFont file. If you use kitty you should also do this as explained [here](https://sw.kovidgoyal.net/kitty/faq/#kitty-is-not-able-to-use-my-favorite-font)
3. Wallpaper - I am using this wallpaper from [pexels](https://www.pexels.com/photo/calm-body-of-water-during-golden-hour-1631677/)

## If you're using a container that can see the config files (e.g. distrobox)
In [starship.toml](./dotconfig/starship.toml) I have it set so that if `OS_CONTAINER` is set, then it will show the `hostname` of the container alongside the prompt itself.

I have this line in my .zshrc to set said env variable if the OS is containerized:
```sh 
if [ "$(uname --nodename)" != "arch" ]; then export OS_CONTAINER=1; fi
```
Replace `arch` with your hostname (Use `uname --nodename` to check said value).


## Hyprland specific stuffs
- [eww's get-current-workspace](./dotconfig/eww/scripts/get-current-workspace) is copied from [hyprland's guide](https://wiki.hyprland.org/Useful-Utilities/Status-Bars/#eww), and should be changed if you are not using hyprland.

- Here's an aesthetic snippet you might want to add if you are using hyprland:

```hyprlang
general {
    gaps_in = 5
    gaps_out = 10

    border_size = 4

    col.active_border = rgba(fab387f1) rgba(e64553ee) rgba(89dcebdd) 90deg
    col.inactive_border = rgba(24273aff)
    # other configurations here
}
```
