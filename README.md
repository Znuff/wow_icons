# Why?

This is a set of tools, scripts and instructions to convert the default World of Warcraft in-game icons that have had different look over the years and expansions to a more uniform look.

This project is a continuation of suicidalkatt's [Clean Icons](https://www.wowinterface.com/downloads/info17774-CleanIcons-Square.html).

# Requirements

This set of scripts is designed to be run under [WSL](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux), but they can be adapted to your specific OS/Environment

  - Ubuntu under WSL1 (not tested under WSL2)
  - A tool to convert **BLP -> PNG** and **PNG -> BLP**, this is provided in the `tools` directory (**BLPConverter.exe**)
  - A 64x64 icon mask, different ones are provided in the `masks` directory
  - [Exported World of Warcraft assets](https://wow.gamepedia.com/Viewing_Blizzard%27s_interface_code)
  - ImageMagick under WSL (`apt install imagemagick`)
  
# Concept

Once you have exported the game assets, you will find the game icons that we're going to modify under the directory `\World of Warcraft\_retail_\BlizzardInterfaceArt\Interface\ICONS`. This directory contains (mostly, more on that later) 64x64 BLPs, each one of them representing different different abilities, inventory items or other UI elements in the game.

As mentioned above, over the years, WoW has had different border-styles for icons, making an overall mess of the styles used. To fix this issue, a lot of addon authors (and players) have resorted to showing in-game icons with different tricks like zooming & cropping the icons, then adding consistent borders to have them all show up the same.

| ![Vanilla Icons](https://imgur.com/aGSo4.png) | ![Burning Crusade Icons](https://imgur.com/hxjs1.png) | ![Wrath of the Lich King Icons](https://imgur.com/0LBHp.png) |
|     :---:      |     :---:      |     :---:      |
| ↓ | ↓ | ↓ |
| ![Vanilla Icons](https://i.imgur.com/kqbrS.png) | ![Burning Crusade Icons](https://i.imgur.com/IULtF.png) | ![Wrath of the Lich King Icons](https://i.imgur.com/40miY.png) |
| Classic | BC | WoTLK |

The process is simple:

1. Convert all in-game icons to `PNG`
2. Apply a mask that covers the original borders to all 20.000+ icons (at the time of writing)
3. Convert the icons back to `BLP`

In order to not cut the icon graphic too much, and to not leave out important bits (for example, the card numbers on the Darkmoon Decks) we will be using a a mask that blanks out `4x4x4x4` pixels with a half-assed attempt at a rounding corner (this is mostly to hide the extra-rounded corners of some **Battle for Azeroth** icons).

For example, the included `64x64_clean_square2_mask`:

![Clean Square2 Mask](https://i.imgur.com/NgTASEa.png)

Mask suggestions (pull requests) are obviously encouranged.

# Acknowledgments

  - **suicidalkatt** for the [initial idea / icon packages](https://www.wowinterface.com/downloads/info17774-CleanIcons-Square.html)
  - **Dandelion** for the [BLPConverter](https://www.wowinterface.com/downloads/info14110-BLPConverter.html)
