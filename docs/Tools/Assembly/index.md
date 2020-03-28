---
layout: default
title: Assembly
parent: Tools
has_children: true
nav_order: 2
has_toc: false
---
# Assembly
{: .no_toc }
### Multi-Generation Blam Engine Research Tool
{: .no_toc }

Assembly, a free open-source Halo cache file (.map) editor, enables creation and distribution of patches for game content. The patch system allows modding of map files without downloading the entire map.

Halo on PC requires the 2019 experimental version of Assembly. Choose this version in the Assembly downloader.

### [Download](https://github.com/XboxChaos/Assembly/releases)
{: .no_toc }

## Guides
{: .no_toc .text-delta }
1. [Poking](Poking/)
{: .custom_toc}
---
# Assembly and Its Functionality
{: .no_toc }
Halo .map files are in the hexadecimal format. All graphics, textures, sounds, models, and characters (bided's) are located in the map files represented as a series of values between 0-9 and A-F. Many games separate map files from other game resources; every map references the same resources in a differing location. Halo does not work this way, every resource is duplicated in every map file. To save space and shorten loading times, unused resources are not implemented into the maps. Example, The Pillar of Autumn (m70.map) mission does not have a falcon. Its related textures, animations, models, and sounds are not present within the .map file. Assembly allows easier editing of the hexadecimal format through transposing it into an easily readable and editable format. Every game object has a block of corresponding hexadecimal code. The developers, through trial and error learned which blocks correspond to which objects and the area they are located within the file. Then they labeled each block and designed Assembly to display the information in its palatable format.

## Table of contents
{: .no_toc .text-delta }
1. TOC
{:toc}
---

## Map Header

The map header, allocated to the first block of every map file, contains the map metadata. This metadata describes elements such as map type, singleplayer or multiplayer, the internal name, amount of tags (objects) in the map, and other technical information. Map files are split into four sections: Debug, resources, tags, and languages. The map header describes these sections and their address locations. The debug chunk represents strings, stringid's, tagnames, and other trivial data related to debugging. The resources category contains compressed tag resource data such as bitmaps, geometry, animation data, bsp collision, pathfinding, shader buffers, and sound data. The tag section consists of tag (object) data in an uncompressed state. The language region defines locale's. Locale's encompass translation data for all supported languages. All readable in-game text derives from a locale string chosen in corolation to the chosen language under the in-game settings.

## Tags
Blocks of code or objects are organized as tags. Every weapon, vehicle, sound, animation, and object are tags. Assembly adds, or edits blocks of code and overwrites the opened file based on the changes the operator makes. Basic modding practice extracts tags from maps and imports tags into maps that did not have those tags. Importing one tag can import many other required tags along with it. However, it may not take all the tags and sometimes an object must thoroughly be checked over and compared with the original for any missing pieces.

Attempting to import a tag that already exists results in it skipping that import (nothing happens). Tags and imported tags cannot be deleted or removed. Doing so would:
> ...cause a lot of problems, and anything deleted wouldn't be truly "removed" from the map. I'd suggest making your modded tags separately, then injecting into a fresh map when you are finished. - Lord-Zedd, Github Assembly Issue #209.

The most important tag in Assembly is the Scenario (.scnr) tag. This tag contains the placement of objects, AI units, vehicles, environment (foliage), and much more. It also contains the map ID and map type (singleplayer or multiplayer). This tag also contains the sandbox_palette and the Sandbox Budget. The palette is the in-game forge editor menu. Adding objects to the sandbox palette adds them to the forge editor menu in-game (Campaign maps require a series of steps to enable forge mode). Enabling all zonesets are required for tags to spawn after added to the sandbox palette. This applies to imported tags and tags Indigenous to that map.

## Scripts
Halo map scripts (not to be confused with megalomaniac game type script editing) are precompiled. This means editing map scripts cannot happen without a decompiler and recompiler, which currently does not exist. In Assembly, Halo scripts are read-only. Map scripts exploit predefined functions that can differ between games. Halo 3 and future games implemented parameters into map scripts.

Script expressions, located in the scenario (scnr) tag are editable script data. This alterable code in a form similar to other tag data, comes with a compexity that creates a difficulty in achieving substantial outcomes.

## Internal map names

A list of internal map names and in-game map names are listed in Assembly under Help → Map Names. Example, m05.map = Noble Actual.

## Important Object Types
This list encompasses the abbreviations for tags often used in regular operation.

Globals = matg  |  Global settings.  
Scenario = scnr  |  Scenario related data.  
Scenery = Scen  |  Scenery related objects.  
Vehicle = vehi  |  Vehicles.  
Weapon = weap  |  Weapons.  
Crate = bloc  |  Objects placed in the environment. Example: pallets.  
Model = hlmt  |  Data related to object models.  
Model = mode  |  Mesh data.  
Shader = rmsh  |  Shader data.  
Sound = snd!  |  Normal sounds such as gun-fire.  
Sound Looping = lsnd  |  Looped sounds such as the sounds of a vehicle engine  
Sound Environment = snde  |  Environmental sounds such as wind and foliage.  
Sound Cache File = ugh! (Do not import this tag it will crash the game)  

## Plugins
Assembly's modular design assigns a plugin to each tag type. Modders can edit or download plugins to alter Assembly to suit their needs. See Plugins.
