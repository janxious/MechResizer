# Mech Resizer

BattleTech Mod (using [BTML](https://github.com/Mpstark/BattleTechModLoader) and [ModTek](https://github.com/Mpstark/ModTek)).

Change the size of mechs on a per-chasis basis. Always wanted a 200 meter tall Locust? Now you can!

## Features
* change the default size of all mechs in game without vanilla json modification.
* change the size of any chassis in game 

## Download
Downloads can be found on [Github](https://github.com/janxious/MechResizer/releases).

## Install
- [Install BTML and Modtek](https://github.com/Mpstark/ModTek/wiki/The-Drop-Dead-Simple-Guide-to-Installing-BTML-&-ModTek-&-ModTek-mods).
- Put the `MechResizer.dll` and `mod.json` files into `\BATTLETECH\Mods\MechResizer` folder.
- If you want to change the settings do so in the mod.json.
- Start the game.

## Settings
Setting | Type | Default | Description
--- | --- | --- | ---
`mechResizeMultipliers` | `json hash` | {} | change the size of mechs using the format `"chassis string" : multiplier float`. A big locust would be like `"chassisdef_locust_LCT-1V": 15`
`defaultMechScaleMultiplier` | float | -1 | defaults to whatever it set in `TEST_MechScaleMultiplier` (vanilla is 1.25). override this to globally change all mechs

Note: neither of those is set with any values by default, so you won't see a change in game unless you change them.

## Screenshots

Big Locust

<img width="885" alt="screen shot 2018-05-22 at 2 08 16 pm" src="https://user-images.githubusercontent.com/50124/40382747-306be6b8-5dcd-11e8-8956-078891fd6722.png">

Big Everythings

<img width="973" alt="screen shot 2018-05-22 at 2 26 07 pm" src="https://user-images.githubusercontent.com/50124/40382748-30800814-5dcd-11e8-8de0-f1943be2af53.png">


## Sample Config

Big Locust, tiny everything else.

```
{
  "Name": "MechResizer",
  "Enabled": true,

  "Version": "0.1.0",

  "Author": "janxious",
  "Website": "https://github.com/janxious/MechResizer",

  "DLL": "MechResizer.dll",
  "DLLEntryPoint": "MechResizer.MechResizer.Init",
  "DependsOn": [],
  "ConflictsWith": [],

  "Settings": {
    "defaultMechSizeMultiplier": 0.25,
    "mechSizeMultipliers": {
      "chassisdef_locust_LCT-1V": 15
    }
  }
}
```

## Special Thanks

HBS, @Mpstark, @Morphyum


## Maintainer Notes: New HBS Patch Instructions

* pop open VS
* grab the latest version of the assembly
* copy the new version of the methods in `original_src` over the existing ones
* see if anything important changed via git