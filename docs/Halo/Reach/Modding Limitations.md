---
layout: default
title: Modding Limitations
parent: Reach
nav_order: 3
---
# Modding Limitations
* The Assembly downloader will download the 2016 main branch. It does not work for the PC version of Halo Reach. Make sure to click the 2019 "dev_" branch.

* Importing sounds from other maps is disabled as that feature is not yet complete. A time consuming method to adding sounds does exist. Importing vehicles such as the falcon will not come with its sound files.
See Map to Map sound injection for more information:
https://www.xboxchaos.com/topic/4815-map-to-map-sound-injection/#comment-38478

* Adding custom models, textures and maps to the game is not possible.

* Editing collision boxes of existing models is not possible. Models need to be imported with their collision information.

* Custom map names are not possible in the PC version of Halo Reach but are possible in the Xbox version.

* The entirety of a campaign map cannot be used as a multiplayer map due to zone loading. The game will crash if it tries to load too many zones at the same time.

* Forge contains two sets of teleporters. The non-forge ones are likely deprecated. Use the ones with the directory labeled "levels\forge" rather than the ones labeled "\multi."

* Campaign maps in multiplayer require editing complex BSP zone loading. Without this modders are restricted to a portion of the map otherwise players will crash.
