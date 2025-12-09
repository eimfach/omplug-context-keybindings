# Context Aware Key Bindings Plugin (cakb) - For Omarchy Linux

> "Key bindings for all the stuff, freshly served, I hope you find them Contextually appropriate, Sir !" 🧐

This Plugin lets you see Key bindings for the active application you are in.
This is mainly a Plugin for Omarchy using Walker, but can be used in any Hyprland configuration.
It basically echoes Key bindings text for Walker according to your active Hyprland Window (Each app needs a separate "yourapp.conf"
but only for generating the output).

## Setup

- Copy or clone the files into `~/.local/share/omarchy.plugins/cakb`

- Add a new entry to your `~/.config/hypr/bindings.conf` to be able to open the key Context menu:

`bindd = SUPER SHIFT, K, Show Context key bindings, exec, ~/.local/share/omarchy.plugins/cakb/bin/omplug-cakb-keybindings`

- Open a terminal (Ghostty) and try `SUPER + SHIFT + K` !

> By now this ships with Key bindings for Ghostty, Zen Browser and Obsidian

## Creating new Context Bindings
To add a cheatsheet for a new app, create a file in `hypr/yourapp.conf` and run `./compile` to create a new `json/yourapp.json` 
(This will open briefly a new hyprland window and then close it for each .conf file).
To get the required filename for your corresponding .conf and app check it on hyprctl (app needs to be open):

`hyprctl clients -j | grep -i yourapp`

The filename is in the property `initialClass`

After the json file was created you are ready to go ! `SUPER + SHIFT + K`

INFO: All .json files can also be overriden in `.config/cakb/youroverride.json`.

INFO: The hyprland .conf files in `hypr/` do not get loaded into your hyprland config.
They are only used to parse and compile appropriate Key bindings for your keyboard to json.
Each file is for the specific application and capitalization matters.

INFO: This plugin can also be extended to show Context Key bindings for the browser tab you are in. The json property for that is `title`.

CONTRIBUTING: Please, feel free to contribute the bindings for you specifig application ! Together we can fit them all and profit.
