


# Animation Inheritance

A step by step guide for setting up and getting Animation Inheritance to work on bipeds using [Assembly](https://epitaph.dev/docs/Tools/Assembly/Assembly/).


Credits
---
[Original Xbox Chaos Guide](https://www.xboxchaos.com/topic/5419-animation-inheriting/)

Special thanks to Lord Zedd's hard work and help. Originally written by Lueth, method tested by Xayth, edited for Epitaph by PaleLebouf.

--- 

For this guide the example will be taking the animations of an elite and having a marine inherit those animations.

First open the jmad tags for both the elite and marine. On the marine make your way down to “New Inheritance List” and select jmad in the inherited graph section. Then specify in the drop down the elite, or whatever source entity you are taking animations from. After that you will need to add in node maps. Because the elite has 67 nodes overall there needs to be 67 nodes added to the marine. Ignoring the Local Node field, it should look like this in Assembly.

![Node Map in Assembly](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim1.png "Node Map 1")

Next is matching the nodes of the marine to the nodes of the elite. Local node refers to the Marines nodes. Starting at 0, both the local and node map are 0. The elite’s node 0 is called b_pedestal. The marine’s 0 is also called b_pedestal. These nodes must be matched. Find and match each node according to the name between both bipeds.

![Node Map Local Node](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim2.png "Node Map Local Node")

Node number 1 for the elite is labelled as b_aim_pitch. b_aim_pitch of the marine is node number 3 so the number 3 should be entered in the Local Node field to match them together.

![Node Map Local Node Filled In](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim3.png "Node Map Local Node Filled In")

Following this pattern, match these node numbers according to their labels until all 67 have a value. There will be times where the elite will have a node with a label that doesn’t exist on the marine (b_l_pinky3 for example). If this is the case, put a -1 in the Local Node field since -1 is treated like it doesn’t exist (or null). There is also the option to find a node that can serve as a “best fit” if there is no direct match, but that depends solely on what biped is inheriting animations from another. 
 
![Node Map Local Node Filled In -1](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim4.png "Node Map Local Node Filled In -1")

After matching nodes in the node map comes work under Node Map Flags. In Node Map Flags, each number column corresponds to the number in a Node Map. Since this is a 32-bit field, only a maximum of 32 Nodes will show up. The other columns represent additional numbers beyond 0 to 31 to help indicate which node number each flag corresponds to in additional chunks. In this example, since there are 67 nodes for the node map, it will have to separated into 3 chunks in total to account for all of the nodes (32+32+32=96 to account for all 67).

![Node Map Flags](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim5.png "Node Map Flags")

Once these 3 chunks are created, go through each node again, and check the box for each node that had a Local Node value that was not -1. For example, nodes 0 and 1 have values that are not -1. That means the corresponding boxes should be checked. For nodes 10 and 11 which did not have a match and have values that are -1, leave their corresponding boxes unchecked (like the image below).

![Node Map Flags 10 and 11](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim6.png "Node Map Flags 10 and 11")

Once the Node Map and Node Map flags are completed, it’s time to apply animations from the elite to the marine. Start by heading up to Animations section of the marine and for the parent, select jmad, and then the elite as shown in the picture below.

![AR Idle Animation Tag](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim7.png "AR Idle Animation Tag")

This is idle variant 463 which is one of the marine’s idle animations for the assault rifle. These variants go up to 466 which is the fourth variant of the idle animation with the assault rifle. Next is finding the animation to reassign over the current animation.

![Ball Idle Animation Tag Elite](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim8.png "Ball Idle Animation Tag Elite")

This is the ball:idle animation and its number is 566 as indicated in the top right dropdown box. This number must be put into the Parent Index field under the Parent of the marine’s animation. This is how it should look:

![Parent Index](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim9.png "Parent Index")

Next you just want to poke it or save it and next time you go in when you do the animation, instead will be doing the animation of the elite…...note we are trying to find the offset cause it kinda looks like this on some animations atm.

Last is to poke or save it, and the animation should be applied to the marine when you perform whatever action triggers the animation that was replaced. Note, some animations might not look the best, and could generate abominations like the screenshot below.

![Final Product](https://github.com/HaloBible/wiki/blob/gh-pages/assets/images/animation-inheritance/anim10.png "Final Product")

Aside from that note, good luck replacing animations and happy modding! 
