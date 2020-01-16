---
layout: default
title: Converting Maps from Campaign to Multiplayer
parent: Reach
nav_order: 3
has_toc: false
---
# Converting Campaign and Firefight Maps to Multiplayer
{: no_toc}
Thanks to Lord Zedd, Gamecheat13, the Halo Mods Discord and the Xbox Chaos forums.

## Loading the map in MCC’s menus
{: no_toc}

As of right now, you can’t add new maps to the menus, so we’re going to have to replace a multiplayer map. You’ll want to backup the map you want to convert and a multiplayer map we’re going to replace it with, if you haven’t already.

First, rename the multiplayer map to something else, but keep the file type intact as we’re going to use it as a reference. Then, rename the campaign/firefight map to the multiplayer map. Now load both up in Assembly and locate the .scnr tag in both.
![Scenario tag](https://i.imgur.com/EKZKeNC.jpg)
We can drag the original .map file so it appears on the right so we can use it as a quick reference and there’s many things we’ll need from it.

To allow the map to even attempt to load, we’ll need to change the map ID of our campaign map to that of the multiplayer map. If you want to be able to save forged map variants, go ahead and change the Sandbox Budget to any number above zero or nothing will save. After you’re done, close the tag so that later the imported objects will appear in it’s lists.

## Table of contents
{: .no_toc .text-delta }
1. TOC
{:toc}

## Tag Extracting/Importing

The next thing you’re going to want to do is extract some needed tags from the multiplayer map. The two most important are the .mulg multiplayer_globals tag and the .wgtz ui\multiplayer tag - you can skip down to Setting up Forge objects if you’re using a Firefight map - they should have all the information necessary, however if you want to learn, read on.
I recommend using a small map such as Beaver Creek or Prisoner for extracting the tags, as the .mulg tag will include vehicles and weapons native to that map.

![Add to extract list](https://lh5.googleusercontent.com/n6ST3f0mYOKJjmBK73WV11kUVGyIhVvUsEhHlGZyWadHXKhcalpNIR_FqwqCNCBKHYOb-b2PGpvRaBIky3bX3wNoz0LNEB21ZMJpLm7s71aTpd7NcrnQxABBGTReDLTvrdUZGQJz)

When you extract tags, there is the option to extract one at a time, however you can also add them to an extract list as seen above which will put all of the tags you want into the same file.
It’s worth grabbing Forge related items you want in your map such as spawn points and objectives, find the Sandbox Palette in the multiplayer map’s .scnr and scroll through the entries to locate the different objects you want - at the very least you’ll probably want an Initial Spawn Point especially if it’s a campaign map.

When you’re done adding things, click Extract All and give the .tagc file a nice name. But before you import it all into the campaign map, go to the campaign map’s mulg tag and give it a new name - remember to click Save Tag Names afterwards. Now you can import your .tagc file, be aware it may take a long time and it’ll look like Assembly has frozen but just wait.

## Switching things up

Now you have your tags in, there’s a few things left to do in order to actually make the map playable. First, head over to the global.matg tag and search for “mulg” and change the drop down box so it points to your newly imported tag - this is why we renamed the old one earlier. Still in the .matg tag, search for wgtz and set both Single Player/Survival UI Globals and Multiplayer UI Globals over to the multiplayer variant - without it accessing Forge isn’t possible.
![Multiplayer globals mulg tag](https://lh3.googleusercontent.com/EHhPm90AEBFHVRvPuKCFQUVt7YyhzCszLaRpF9IkvSHrwP2GVT6SA0lhbMfFRbC_armYaOo1C3nwcnjlxUFWMlLPBRhY803V5iZCf0A)

![Multiplayer globals wgtz](https://lh3.googleusercontent.com/hmjCrtmRrmOScXpnC_h0zOanvdp1talImUUCaShidSpsysSYXaTKq_5fIMtydDFI2FNwuUWqGlJUZA9ZAVXko9_gTLxpSKD5AFxtBMyZPyjulWp1-2SkWIKcAF6gB6QRHm3ffG0w)
Now we’re going to head over to the .scnr tag - there’s two things we have to do here, the first is to go over to the Scripts block, hit the i symbol and change the count to 0, then do the same for the Globals block. By changing the count to zero we can stop any scripts from attempting to trigger and crashing the game whilst still preserving them all should you ever want to try your hand at adding some to the level - just change the 0 back to whatever it was originally and they’re back.

This next part may not be necessary if you’re using a Firefight map, but it’s probably worth doing anyway just in case - if your map loads but you’re faced with a black screen and can’t spawn, it’s because your spawn isn’t working.

![Tag Block Reallocator](https://lh3.googleusercontent.com/jM_t5Py_pRUN3oE8Km1alG41DpfB4d8JFXgo9a-qugT7Z_5qBHiuoyvKy0v1sVVnxOwGttYFs-pBf_QHjuQFf-Jlp1bXfUwaGsfO8K1KdUuLOvvZTVV0fJck57Rpxb5PsuGV0q-1)

Find the Scenery Palette and add a new entry with the plus symbol, after reallocating you’ll now have a new number at the bottom of the drop down. Change the tag type from null to scen, then change the object to be the initial spawn point that was imported from the multiplayer map - this allows us to place a spawn point in the map without using forge. Above the scenery palette you’ll see another block labelled just Scenery, add another entry to this like you did with the palette.

![Scenery section](https://lh3.googleusercontent.com/86NmnqVKxVM5yljBP2SMS4s_qtNl63n0w0M-Bj9x68ncHROcbkmyzf0Bx-wB4TdJC1P9KXDnv8veO3lvp0Na02eimgzNrGwcTuH9Z7o_Bdy3FifOvZheoi6QZmmjVLoepews3wri)


The Palette Index is the number corresponding to the item in the scenery palette, it works this way with all other types of objects as well. Set this to the palette number of your initial spawn point that we created in the previous step. Next you’ll see Position X,Y,Z - in order to guarantee you won’t spawn into the void you’ll want to search for the Player Starting Locations block - grab the coordinates from there and copy them into your new scenery tag.

![Scenery section 2](https://lh3.googleusercontent.com/Wth3nBtBBvz4Tl5YZpZhWdcgdEEstyfbuuLzV1MTCuqxntUXcGE7OTPGLuf5GdQJc4wX_tLjumW6iZc86V8k8quycqlEGCED0_rmt5zoZcvOQth-kTvBLovBCfjgwTxivlE3VBO2)

Lower down in the Scenery block you’ll see Type and Source - switch these to Scenery and Editor respectively. Now you’ll want to edit the Allowed Zonesets, these are the finicky buggers that determine what area of a map loads what resources - for now just right click and select all so your spawn point will appear regardless of what portion of the map is loaded.

![Multiplayer data](https://lh3.googleusercontent.com/vefffAEfLBZ_vKe9JasWcO4XBWbiHneqgU_nbnyBuvJFybWVwyKZjiLodBCZ991aCtANKItOTxhtnnmgIPDjNu5jApmTceaT_fSsuLI)

Lastly, change Team in the section above to Neutral so you can spawn in regardless of what team you’re on - it defaults to Red, which is the same as the Forge default but it’s good practice in case you ever want to play with friends.

## Elite Player Models

In the campaign, the player is always a Spartan - it wouldn’t make a lot of sense if they allowed people to play as Elites there. This isn’t normally a problem, except when you  import a campaign map to multiplayer and you try to play as an Elite it can’t find the required information, so it just doesn’t allow you to spawn in. Firefight fortunately does not have this issue, but for campaign maps there are some steps that need to be taken.

We can either import the Elite bipd and first person models, which may make multiplayer black screen if you’ve imported a lot of other tags, or we can set the Elite models to a Spartans, either way you’ll want to go to the Player Representation block in the matg tag, as seen here:

![Player representation](https://lh4.googleusercontent.com/vGDqTquv-uGC1U81FkZL4jShsHzp0fEO0MLduciXtPrciDb6b6KCbnP8eEygfC7dXeJqIeP9v6YrEaWX6UViyFlNFSL48WHrVqecZIBuAr5eFjpDNlaDntsqaEksGWQAs1D0a8hW)

By default, up in the top right it will have 0, that is the Spartan’s representation. The second entry is for Elites and this is what it will look like by default. To make Elites spawn in as Spartans, we’ll first need to copy all of the information from the Spartan representation to the Elite representation, or copy the proper Elite information from a map with it to make them spawn properly as Elites. This will allow Elite players to spawn in, however you may notice some issues..

The first obvious one you’ll notice is that most of the weapons you use don’t have a first person model or animations. Much like the player representation in matg, each weapon has a model/animation block for player types called First Person with two entries. If you’re not importing an Elite model, instead of having to enter the information for each weapon we can instead click the i symbol and set the Count to 1, forcing weapons to use the Spartan information, but we’ll still need to go over each weapon doing this.

![First person section](https://lh6.googleusercontent.com/1xhsop3-Ru2HtWDpuBAGIaZzTwcb-bOdGv0wla38RF9E7uc_CY4aC75xTxosJQ-C4kvFl-uQeeTtTkpaeXFQZVwSiZ-vfF_WKni88_8X)

The second issue will only be for the pseudo “Elite-Spartans”, you will notice a lack of arms when viewing your character in third person. This is because the game is trying to apply the Elite armor permutations to Spartans, but we can fix that. Navigate to the .pmcg tag and scroll down to the bottom. You’ll notice Spartan Base and Elite Base - in the region section, the Spartan’s first entry is arms, whereas the Elites first entry is head. All we have to do here is change the Elite’s region names for each entry to match the Spartan Base first three entries. There is of course no need to do this if you have imported the Elite model instead.

![Elite base section](https://lh3.googleusercontent.com/23rErBw6Yh87TOH6JpsIDzF1zq0_mXjUtI_TfHHnnfgw1u0qlyphnupQIh73tzSoCLbd0oWxsmtnc-j88rEktyN7L_pQS5emNRPp46VOiPfDz44DxAo8bdwzFz-kznElzjcuQWve)

Thanks to Arttumiro for identifying this issue.

## Spawning in

If you’ve done everything above, saved it all and double checked it, you should be ready to go. Load up MCC without anti cheat, switch out your .pak so you can play Forge and load the map under the multiplayer map name you chose. If it worked and you’re where you’re supposed to be, great! You can move on to the next section.

Buuuut it probably didn’t, because let’s face it these things rarely work the first time. Here’s what you can try, assuming your map does load and not just crash to the desktop.

Adding the initial spawn point to the sandbox palette - see below, this may be necessary to spawn at all in the campaign maps
Slightly raising the Z coordinate for your respawn point to make sure it’s not getting stuck in the ground
Looking up the Squad block and changing the spawn point to that of one of the Single Locations listed for your AI teammates that would normally spawn in the level
Heading over to the Scenario Zoneset Groups block and checking Loaded Designer Zonesets and unchecking Unloaded Designer Zonesets for each group
Just randomly changing the coordinates to random squad locations
Loading a different BSP (a bit complicated for a bullet point)
Switching your player model preference to Spartan - see the new Elite Player Models guide update for more information

If you’re crashing before you can even load the map your best hope is going over everything here and making sure you followed each step properly, if you did and it’s still not working there might be an issue with that map that’s beyond my current knowledge.

## Setting up Forge objects

So your map works, you can load in and fly around, but your forge menu is empty, you can’t place anything. This is where the Sandbox Palette comes in - the Sandbox Palette contains all of the entries for the forge menu. In order to set it up, it’s best to use the old multiplayer map as a reference, but note that since it’s a campaign map not all of the items from multiplayer will be available and even with injection won’t work properly. Be aware that if you alter the Sandbox Palette after creating map variants they may no longer function so finish up everything you want to do here before going at it.

![Sandbox palette section](https://lh5.googleusercontent.com/1BWNLxyCBzi540mpj-4e0bpZC0HfAKhT7H4_KlcRZJHTvzspjP4LV3lREgzlQGQq4OdiwY9gXLwMNwKkWw5I0ipMf54ZoM_bl5m7EG444zys3YVwG6JH_0tipJ4ZOCWKKmHCev0I)

The first level of the Sandbox Palette is where you’ll have your entries, ff_spawning for example contains the initial_respawn_point entry, which itself will need an entry variant with the object tag - you don’t need to worry about adding a name for the variant unless there are multiple such as with the Warthog or Falcons.

You can leave the Entry Count and Entry Price at 0, so long as your Sandbox Budget has a value above one it doesn’t matter. The Thorage value presumably controls whether the item originates from Thorage or not, just leave it at 0.

I made a document that lists all [Forge World entries](docs/Halo/Reach/Sandbox%20Palette%20Objects/) for convenience, let me know if there’s anything I should improve there and like this document feel free to add suggestions.

It is also possible to inject the Sandbox Palette from another level by duplicating the .scnr in that map. You would then null out everything but the parts of the Sandbox Palette you want - keeping in mind that vehicles and thorage objects are known to sometimes cause issues on import - and extract this tag. After injecting it into your map, you would then take the Address of the injected Sandbox Palette and copy that into the map’s regular SCNR.

![Sandbox palette section address](https://lh3.googleusercontent.com/h8gLtNXKrmSEhEO7W5ROuH7S78jiORb1ew02rmSAWKidmysSWEbpM68I5zDkDfhfSeXzgaxFV4JiiFOxKd0HKuYmfpNnhD8kvUqv6GJvdFsdg8qEvEWKHxCsbEH2k4us4jGlax4d)

This can be tricky and I recommend making backups, but could also save you a lot of time. Thanks to dany for making the initial suggestion and Lord Zedd for showing me how to get it to work properly.

## Gametypes and .motl

If you want your map to have game types other than Slayer like Capture the Flag or Assault, you have to match your imported objects to the Multiplayer Object List found in the global.motl tag - this will also allow you to spawn in with imported weapons should you match those up as well.

![Multiplayer object list in globals](https://lh5.googleusercontent.com/dYqOemPQSWplN7fgsanma1PCrMBUAV8w1e4zkZ3B7wdd_KekUgSGyYf4pm6eVbCmy-ScTOFymE5SH61eYFc5TXCA7PSRAIxuWMf5UI-rcmleEPY4vYaLaxOgli6znGsGwNOIhmsa)

While some objects such as the Invisible Cube of Derek may seem like they’re random or pointless, they can actually be very important - the Invisible Cube of Derek/Alarming objects enable game types such as Oddball, King of the Hill and Invasion to work - so don’t be like me and neglect to put them in.

Many thanks to Lord Zedd for showing me how to do this.

## My object isn’t spawning!

There are a few different reasons why this might be and I know of at least two. The most common reason is because the Designer Zonesets are blocking it - you can try going to the Scenario Zoneset Groups block and checking all the sets as previously detailed in the Spawning In section.

Another reason it wouldn’t spawn is if your object doesn’t have the Multiplayer Object Properties block - go to to the object’s tag and add one in if necessary, the relevant parts are the Object Type, Spawn Timer Mode, Spawn Time and Abandon Time, as far as I know you can leave everything else as is.

If you’re outside the normal map bounds, head over to the Structure BSPs block in the .scnr tag and check each entry for the Prevents Forging flag, untick that and you should be good to go.

If all else fails, you can forceload a tag by right clicking on it in assembly and clicking “Forceload” and it’ll make the tag act as if it had been injected into the map - Thanks to Lord Zedd for showing me this!


## Alternate BSP Loading

So you’ve got the map loaded and working, but you’re not in the area you’d like. Campaign map areas are split up into BSPs, which are then loaded as part of BSP Groups. Loading different areas can be quite tricky, as often a single mistake will cause the map to crash, but with some luck you’ll get it working.

First, find the Scenario Zoneset Groups block in the .scnr tag. It should look something like this:

![Scenario zoneset groups](https://lh4.googleusercontent.com/zM51VflnmBAk_i1RSBRQeKUdnVb_zJv61b5MgOq99h8j1A1TZGkaflG8EUpqMwbGsuC2WlxUb_kr-wypGxHxXiCc02mYlN8VmK-cHjZF3a7Ubg2H9eD-VMugPn_pReKzzcy6RoZe)

It looks like a lot, but it’s actually just as simple as copying a few numbers. In the block’s top right drop down, find the group you want to load into. Sometimes it’s obvious which is which from the names, other times you’ll need to experiment.

From the group you want to load, note down the BSP Group Index, Loaded BSPs 1 and 2, Scenario BSP Audibility Index and it’s probably wise to change the Unknown fields as well. Don’t worry about the Name and Name String, and you shouldn’t need to do anything with the Unknown 6 block either. If you’ve read the other parts of the guide you might recognize Loaded/Unloaded Designer Zonesets - personally I tick all of the Loaded and untick all the Unloaded, but it’s up to you if you feel that’s necessary for your map.

Now, assuming you do all of this correctly you might still have issues getting in. This is likely because your spawn point is in a different area, so what I recommend is going into your new area in the campaign, noting down a fairly unique object and finding it in the .scnr and swapping your spawn point location over to the one the object uses.

When moving around in the map, you might accidentally load another area - this is fine if you’re on your own, but causes issues in multiplayer, so I recommend finding the Zoneset Switch Trigger Volumes block and setting the Count to 0 so it won’t happen, unless you don’t plan on playing the map with anyone else.

It is also possible to load BSPs in a different configuration to what would normally be seen in the map, however that’s not something I myself have fully figured out yet so I won’t be covering it here - what I will say is that it seems to require you to alter or create a new BSP Group in the block of the same name.

Other common issues

If your Phantom, Spirit or other vehicle is falling through the world, go to it’s .phmo tag and change all the Unknown Interaction fields to -1 and the Interaction Unknown fields to 0 - See Lord Zedd’s topic on XboxChaos
Some vehicles such as Pelicans, Phantoms and the Spirit are difficult to enter for non-host players - increasing the entry radius of the seat can help.
If you can’t access the forge menu you need to set the Multiplayer UI Globals to ui\multiplayer in the .matg tag.
In multiplayer non-hosts will sometimes have a black screen or won’t be able to see objects that you’ve imported from other maps. This is usually vehicles and bipeds but I have also seen it happen with some Thorage scenery objects. The cause of this is unknown, so I advise caution and repeated testing when importing any object that falls into the above categories.
Sometimes the Forge menu in-game has issues remembering your place, try this fix from Wafflexboy on XboxChaos if it becomes a problem
Final words

If you’re an experienced Halo modder it’s probably pretty obvious from this tutorial that I don’t really know what I’m doing - you’re welcome to copy this document and correct all the wrong parts, I’d certainly like to know.

If you’re a new modder like me and none of this worked, sorry! I’m still pretty new and you might have to ask for help from someone more experienced. But hopefully at least some of it worked out ok and you had some fun with it, I know I did.
