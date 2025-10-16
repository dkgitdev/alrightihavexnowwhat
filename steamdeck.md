SteamDeck
=========

# Shortcuts (EASY)
The STEAM and the *** keys are interchangable in SteamOS' shortcuts and will be referenced as `S`.

Hold either key to get full list of shortcuts shows.

Notable mentions:
- `S + L1` – magnifire glass mode
- `S + R1` - screenshot
- `S + X` - on-screen keyboard

# Issues

Various nasty stuff. Even Valve isn't perfect.

## Keyboard / in-game Overlay (like thouchpad menus) not visible and not interactible. (EASY)

Solution: reboot.

Notes: This happens a lot more frequently when using Decky.

# Frame generation via LS (NORMAL)
1. Install Decky
2. Install [decky-lsfg-vk Plugin](https://github.com/xXJSONDeruloXx/decky-lsfg-vk)
3. configure in plugin the settings you want for a game / globally
4. Copy command from plugin and set it in the game's properties.
5. Run game and ensure it's working.

Notes:
- Decky plugin and decky itself is an easy way to install and configure lsfg-vk, but once you're done they can be removed. Just keep the game's start command custom, and it'll be fine.

## Video Editing UI is slow and inefficient
Try using it under desktop mode. Locate it at the top "View" menu.

# Third party apps

## Installation and launch (NORMAL, but a bit time-consuming)

### Intro

After you add anything to steam, you have to manually set "Compatibility" to some version of proton and, perhaps, set prefered steam input method, as default may not get it correcty.

When we add anything to steam, steam creates new folder in steampapps path (TODO) and the "drive C" resides there.

### Portable apps
The third-party stuff needs to be added from desktop by right-click and executable and "Add to Steam". Don't forget about compatibility and controls.

Note: the "delete from Steam" does **NOT** delete the external folder.

### Installers
For installers it's a bit more complicated. 

So when you install game into default drive, it gets installed to steamapps and gets removed when you "remove from steam" it.

#### Installing
While installing you only "Add to steam" **ONCE**! This is because installers may install dependencies and DLCs to the already installed game and adding them separately adds another "drive C" folder, so the game **will not launch**.

- Add installer to steam via right-click
- setup the compatibility and controls (mouse only should do)
- launch setup and install as usual
  - to install DLCs and so on modify the path of library entry, so:
    - binary is pointing to installer exectuable, and its path is **taking into quotes** (`"/like/this/diablo/diablo-dlc-installer.exe"`). You can use on-screen keyboard for quotation
    - working directory is pointing to the folder with executable (no `"` required)
  - launch the dlc installer, install, repeat for all
- find the executable under steamapps folder. The folder don't have understandable names, so sorting on "last modified" should do
- now you need to modify "installer" entry in your library, so that:
  - binary is pointing to exectuable, and its path is **taking into quotes** (`"/like/this/steampapps/diablo.exe"`). You can use on-screen keyboard for quotation
  - working directory is pointing to the folder with executable (no `"` required)
- modify contorls to game-specific stuff
- launch the game from steam game mode

### Something is not launching!
When you have something not launching and you have done everything correctly, you may have issues with...

#### CD protection
Some old games needs their CD installed to the CD-ROM. In linux it's quite complicated, so you may have to fallback to some piracy solutions to bypass the protection, even when you bought the game.

#### Dependencies
Sometimes the game needs some stuff like direct-x or c# redistributable packages.

First you need to know what needs to be installed. It's usually can be reversed from error message.

Second, you need to install it. For this you download ProtonTricks (from shop in desktop mode) and select the installed game, "...default wine prefix...", something like "...install DLL or library...". Select the ones you need to install and try launching again.

## Save backups (NORMAL)
[Ludusavi](https://github.com/mtkennerly/ludusavi) is a fast and mostly intelligent game backup app. Recommended. Although it tends to backup steam games as well, so be sure to untick it on preview. Also it doesn't always see new games, so you might need to add your own save paths. Those can be found on [pcgamingwiki](https://www.pcgamingwiki.com/wiki/Home) page of a game.

# Additional stuff

# Enable SSH for remote terminal access
Remember to keep it key-based, so it won't be a scurity issue. I will not dicuss how, as if you don't know what it is, steam deck is not a great start :)

## Nix as package manager for package persistance between updates (HARD, but allows easy software install later)
It's gonna hurt (two systemd units and a bit of sudo stuff) but [here's the manual](https://determinate.systems/blog/nix-on-the-steam-deck/).

## Syncthing via home manager
TODO

# Devices

# Dock
There are some docks with NVMe drive solt in them. This might be handy if you're using your deck as the only PC or want to setup a TV- / Home-game-library with bigger storage. 

# Wired Headphones
Bluetooth headphones have latency (which is annoying in rythm games) and can discharge quickly than your charging deck (on an airplane or train), so it might be handy.
