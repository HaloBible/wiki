---
layout: default
title: Poking
parent: Assembly
grandparent: Tools
nav_order: 3
---
# Poking
Assembly's poke feature enables modders to modify a map live in-game. This feature works on Xbox and PC. Operators cannot save, increase the length of arrays and indexes, or import tags while in-game. Editing values such as coordinates allows faster editing without restarting the game.

![Poke button](https://user-images.githubusercontent.com/7255464/72213323-349cd700-34aa-11ea-8911-c101bfbc3e3b.png)
The poke button.

## Network Poking

Network poking, located under Tools → Group Poking, allows live editing while connected with other players. It creates a server that syncs modifications with all in-game players. This prevents desyncs. Any player can host the Network Poking server. All players should load identical maps and mods.

Hosts that posses routers without uPnP support will require port forwarding the router before players can connect to their networking poking server.
Players that have never port forwarded a router should review [this guide](https://www.noip.com/support/knowledgebase/general-port-forwarding-guide/) or another suitable one found on the world wide web. [portforward.com](https://portforward.com/router.htm) has a substantial list of routers and working tutorials for port forwarding.
Hosts must share their external IP address with players who want to connect to their server. This address can be found by typing "what is my IP" into Google. However, hackers can exploit this insecure practice which means applying caution to protect privacy through not sharing the address publicly.

Connect to a network poking server before loading the map.

More than one player modifying the same object may crash the game. Other player alterations are not reflected in Assembly. After navigating to a tag modified by another player, click the arrow to the right of the reload buton, and click "Reload From Memory" to update the tag.
![reload from memory](https://user-images.githubusercontent.com/7255464/72213666-eb4f8600-34af-11ea-934e-1534ae7317bd.png)
