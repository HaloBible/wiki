---
layout: default
title: First Person Assassinations
parent: Reach
nav_order: 5
---
# First Person Assassinations

---
Foreword
---

A guide for switching assassinations in Halo Reach to first person. 
Originally written by Arttumiro, edited and reformatted for Epitaph by Occult Outcast.

Don’t follow my values, they aren’t perfect as I spent at least 5 minutes on making it first person. Your camera will go inside your head in most assassinations unless you change the values. 

![Video: Camera inside head](https://i.gyazo.com/08aa2d45c2502119f3bd46346bf21e74.mp4)

---

First, navigate to the biped to enable first person assassinations with, this tutorial will use spartans.bipd, so the playable spartan.

In the bipd tag, search for assassination camera, null out the camera tracks (press the i button and set the count to 0, and set the Camera Marker to head1.

Once done with that it should look like this:

![Assassination camera](https://i.imgur.com/BhHq5yY.png)

If everything has been done correctly then step one is done. Now press the save button as when adding a new StringID it is necesary to save it into the map.

Next is the harder part, go to the mode of the bipd, this tutorial will use spartans.mode.
Find nodes and add a new entry like so:  

![Video: Adding a new entry](https://i.gyazo.com/758067bfc3a3b697d250c8ab5788e78e.mp4)

Then go to the original head node, for spartans it’s the 42nd node and should look like this, note these values down.

![Node 42](https://i.imgur.com/mSW4AEu.png)

Now go to the newly created entry in the block, which will be the last one, which will be 82 if others have not been added. Give it a new name and copy all the values from the original helmet node into it.
It should look like this; the same as above, but with scale set to 0 and a new name that should be easy to remember.

![Copied Node](https://i.imgur.com/aNYFFNz.png)

After this, create a new Marker Group, doing the same as above on adding a new entry. Once this is done, go to that marker group entry and name it head1, or what was used in the first step. Then look through the marker groups until you find one called head, which should be at index 23.

Copy the address of the marker as shown here and place it into the Markers block in the newly made head1 entry, it should look like this:

![Video: Copying address](https://i.gyazo.com/30d77d61ce4d94333c80505e85a39525.mp4)

Next, add 1 to the count and isolate the shared block as shown here:

![Video: Isolating block](https://i.gyazo.com/17291564e9830061ae20649637137755.mp4)

The consequent step is setting the node index to the newly created one, in this tutorial it is 82. These are an example of values that worked well when assassinating Elites and Grunts:

![Head marker](https://i.imgur.com/9G3Ekwl.png)

Once these changes are saved the first person assasination camera should be functional. 
Translation X controls the height and Translation Y controls forward and backwards.
This will work fine for most assassinations with some tweaking of the values.
