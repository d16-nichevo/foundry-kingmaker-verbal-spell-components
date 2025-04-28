# Foundry Kingmaker Verbal Spell Components

Adds a soundboard to Foundry allowing you to play verbal component "chants" from the Kingmaker CRPG.

![Screenshot of this module's dialog](/screenshot.png)

If you're not familiar with the Kingmaker CRPG, your characters will speak the verbal components of their spells aloud, and will use consistent (though [made-up](https://www.reddit.com/r/Pathfinder_Kingmaker/comments/gbh5yr/comment/fp98a35/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1)) words, and will use different intonations depending on the levels of the spell, with higher levels involving more intense chanting.

I thought this could be fun to bring to my TTRPG games in Foundry. This can suit many RPG systems, especially Dungeon and Dragons as well as Pathfinder First Edition, but really others where some mystic chanting would be suit.

* What is Foundry VTT? See [here](https://foundryvtt.com/).
* What is Kingmaker? It's [a CRPG video game adaption](https://en.wikipedia.org/wiki/Pathfinder:_Kingmaker) of [a Paizo adventure path](https://paizo.com/store/pathfinder/adventures/adventurePath/kingmakerap) for [Pathfinder](https://paizo.com/pathfinder).

# Installation

Installation is easy. See [here](https://foundryvtt.com/article/modules/), and read about "Installing New Modules" and "Installing via the Manifest URL".

The manifest URL is:

```
https://github.com/d16-nichevo/foundry-kingmaker-verbal-spell-components/releases/latest/download/module.json
```

Make sure you also enable the module in your game! See "Activating Modules" [here](https://foundryvtt.com/article/modules/).

# Setup

After installing and enabling, you will see two new [Compendium Packs](https://foundryvtt.com/article/compendium/) labelled "Kingmaker Verbal Spell Components".

## Macro

In your compendia, you will see a [macro](https://foundryvtt.com/article/macros/). You can drag and drop this macro to your macro hotbar (instructions [here](https://foundryvtt.com/article/macros/)).

## Playlist

In your compendia, you will see a [Playlist](https://foundryvtt.com/article/playlists/). You can import this if you wish, to get access to these sounds using the Foundry Playlist interface.

## Player Access

By default, your players will not see these compendia items. To correct this, see [here](https://foundryvtt.com/article/compendium/); look for "Compendium Context Menu Options".

# Setup

When clicking on this macro you will be presented with this dialog (or something similar, it may have been updated since):

![Screenshot of this module's dialog](/screenshot.png)

Click one of the buttons to play a sound.

Note that:

* The top three rows are for male-sounding voices. The bottom three rows are for female-sounding voices.
* For each combination of [tradition](https://aonprd.com/Rules.aspx?ID=202), [school](https://aonprd.com/Rules.aspx?ID=214), and voice-type there are three "intensity levels". In the game, the intensity corresponds with the level of the spell being cast.
* For each combination of tradition, school, voice-type and intensity there are a handful of different sounds. One is picked at random.
* If you want a better idea of what they're saying, see [here](https://www.reddit.com/r/Pathfinder_Kingmaker/comments/gbh5yr/comment/fp98a35/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1).

# How To: Extract Sounds from Kingmaker

This isn't necessary to know to use this module. It's mainly in case any other developer is curious.

1. Install or Download Kingmaker, such as [from GOG](https://www.gog.com/en/game/pathfinder_kingmaker_explorer_edition).
1. Inside the install directory, go to this location:
   * `/Kingmaker_Data/StreamingAssets/Audio/GeneratedSoundBanks/Windows`
1. These are `wem` files. There are many tools to convert them.
   * I used [foobar 2000](https://www.foobar2000.org/).
     * I believe you also need these:
       * [foobar2000 Free Encoder Pack](https://www.foobar2000.org/encoderpack)
	   * [vgmstream decoder](https://www.foobar2000.org/components/view/foo_input_vgmstream), see [here](https://wiki.hydrogenaud.io/index.php?title=Foobar2000:How_to_install_a_component) on how to install
1. There are heaps of `wem` files... which do you need?
   * Open `SoundbanksInfo.xml` in the directory mentioned in step 2 above.
   * Look for clues in the `ShortName` or `Path` elements. For instance, to find verbal components, I looked for "Chant".
   * Then find the corresponding `File Id`, for example `File Id="10968175"`. That's the filename of the `wem` file.
   * I used [Notepad++](https://notepad-plus-plus.org/) to whittle down to the lines I wanted, then created a batch file that would mass-rename to a more useful filename, as seen [here](https://github.com/d16-nichevo/foundry-kingmaker-verbal-spell-components/tree/main/sounds).
1. If you are indeed interested in chants...
   * The `ShortName` tells you a lot already: `Arcane_Male_High_11` tells you it's the arcane tradition, a male-sounding voice, and a "high intensity" casting.
     * The `11` tells you the spell's school. A number corresponds with a school: all sounds ending in `11` are Abjuration, for example. Schools have several numbers (Abjuration is `11` and `12` for example. I kept the numbers on my filenames so see [here](https://github.com/d16-nichevo/foundry-kingmaker-verbal-spell-components/tree/main/sounds) for easy reference.
   * [This post on Reddit](https://www.reddit.com/r/Pathfinder_Kingmaker/comments/gbh5yr/comment/fp98a35/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1) helped a lot.