# wlogout
![Example](example.png)
> wlogout is a logout menu for [wayland](https://wayland.freedesktop.org/) environments that support the layer shell protocol
## Running
Run `wlogout` to launch and press escape to exit; Note wlogout only functions in wayland environments that support the layer shell protocol. Any window manager or desktop environment using [wlroots](https://github.com/swaywm/wlroots) will likely work.
## Config
If you editing the default layout and css file it is recommended that you copy `/etc/wlogout/layout` and `/etc/wlogout/style.css` to `~/.config/wlogout/` and change them there.
### Layout
Custom buttons can be defined and edited in a layout file. The format is as follows:
```
{
    "label" : "CSS Label",
    "action" : "command to execute when clicked",
    "text" : "text displayed on button",
    "keybind" : "character to be bound"
}
```
Check the default [layout file](layout) for examples and run `man 5 wlogout` for documentation.
### Style
wlogout can be easily styled through the style.css file; If you would like to style a button use the label given to it in the layout file, and for other styling refer to the [GTK Manual](https://developer.gnome.org/gtk3/stable/chap-css-properties.html) which shows all the allowed css.
## Install
### archlinux
Arch users can use [wlogout](https://aur.archlinux.org/packages/wlogout/)
```
yay -S wlogout
```
### Compiling from Source
Install dependencies:
* GTK+  
* [gtk-layer-shell](https://github.com/wmww/gtk-layer-shell) 
* GObject introspection
* meson
* scdoc (optional: man pages)
* systemd (optional: default buttons)
* swaylock (optional: default buttons)

Run these commands:
```
git clone https://github.com/ArtsyMacaw/wlogout.git
cd wlogout
meson build
ninja -C build
sudo ninja -C build install
```
## License
Wlogout is licensed under MIT. [Refer to LICENSE for more information](LICENSE)
