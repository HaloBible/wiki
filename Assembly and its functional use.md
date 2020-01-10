-Halo .map files are in the hexadecimal format. All graphics, textures, sounds, models, and characters (bided's) are located in the map files represented as values between 0-9 and A-F. Many games separate map files from the other resources; every map references the same resources. Halo does not work this way, every resource is duplicated in every map file. To save space and shorten loading times, unused resources are not implemented into the maps. Example, The Pillar of Autumn (m70.map) mission does not have a falcon. Its related textures, animations, models, and sounds are not present within the .map file. Assembly allows easier editing of the hexadecimal format transposing it into an easy to read format. Every game object has a block of corresponding hexadecimal code. The developers, through trial and error learned which blocks correspond to which objects and the area they are located within the file. Then they labeled each block and designed Assembly to display the information in a palatable format.

Blocks of code or objects are organized as tags. Every weapon, vehicle, sound, animation, and object are tags. Assembly adds, removes, or edits blocks of code and overwrites the opened file based on the changes the operator makes. Basic modding practice extracts tags from maps and imports tags into maps that did not have those tags. Importing one tag can import many other required tags along with it. However, it may not take all the tags and sometimes an object must thoroughly be checked over and compared with the original for any missing pieces.

Attempting to import a tag that already exists results in it skipping that import (nothing happens). Tags and imported tags cannot be deleted or removed. Doing so would:
> ...cause a lot of problems, and anything deleted wouldn't be truly "removed" from the map. I'd suggest making your modded tags separately, then injecting into a fresh map when you are finished. - Lord-Zedd Issue #209

The most important tag in Assembly is the Scenario (.scnr) tag. This tag contains the placement of objects, AI units, vehicles, environment (plants), and much more. It also contains the map ID and map type (singleplayer or multiplayer). This tag also contains the sandbox_palette and the Sandbox Budget. The palette is the in-game forge editor menu. Objects placed in the palette show up in-game (Campaign maps require a series of steps to enable forge mode). Much fiddling is required to make tags work in the palette. Whether an object already exists in the map or was imported.

Halo Reach uses precompiled campaign map scripts. This differed from past games where scripts were compiled at run-time. This means Halo Reach scripts cannot be edited. In-theory, scripts could be edited and then compiled but this has only been done in a limited fashion. In Assembly, Halo Reach scripts are read-only.

Inner and outer map names are listed in Assembly under Help > Map Names. Example, m05.map = Noble Actual.

## **Important Object Types**
This list encompasses the abbreviations for important objects or tags used in the game.

Globals = matg  
Scenario = scnr  
Scenery = Scen  
Vehicle = vehi  
Weapon = weap  
Crate = bloc  
Model = hlmt  
Shader = rmsh  
Sound = snd!  
Sound Looping = lsnd  
Sound Environment = snde  
Sound Cache File = ugh! (Do not import this tag it will crash the game)


## **Current Issues in Halo Reach PC**

The downloader will download the 2016 main branch. It does not work for Halo Reach PC. Make sure to click the 2019 "dev_" branch.

Importing sounds from other maps is disabled as that feature is not yet complete. A time consuming method to adding sounds does exist. Importing vehicles such as the falcon will not come with its sound files.
See Map to Map sound injection for more information:
https://www.xboxchaos.com/topic/4815-map-to-map-sound-injection/#comment-38478

See basic tag injection for more information:
https://www.xboxchaos.com/topic/3938-basic-tag-injection-tutorial/#comment-30825
