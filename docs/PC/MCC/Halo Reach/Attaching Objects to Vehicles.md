-The objects section under variants in the HLMT tag allows the addition of objects to a vehicle. Not to be confused with attachments. The markers section under the model (.mode) file allows positioning these objects.

First open a vehicle to edit, then goto its HLMT. This example uses the semi-truck (truck_cab_large).
![Goto models](https://user-images.githubusercontent.com/7255464/71775002-58a26a80-2f36-11ea-894e-031c024868a0.png)

Remember to set the correct variant of the object on the right. If you want your object to only apply to a certain variant select relevant index. This guide uses "bed_long_container" (The version of the semi that has a container/box trailer attached).
![hlmt variants](https://user-images.githubusercontent.com/7255464/71775058-60aeda00-2f37-11ea-8b32-cf4a4d7f5836.png)

Ignore regions and permutations. Perhaps someone can define what those sections do.

First increase the index list of the objects section by one.
"Parent Marker" sets what your object attaches onto the vehicle. Give it any name you choose. I would suggest name_hitch_mod, allowing easier editing if anyone wants to modify your mod.
Child marker presumably adds a bit more control over how the attaching object coordinates itself. This seems necessary for trailers. In many cases it can be left blank.
Object Variant presumably allows the defining of your object only showing up on certain variants. In most cases it can be left blank as the object is added to the variant listed above under "Variant."
Choose an object under Child Object. Vehicles work fine. In this case we want to attach a controllable weapon to the semi-truck. Notice the object is a vehicle type object and not a weapon type.
Sometimes the first unknown box under Child Object is set to -1. It can be left blank.
![hlmt variants](https://user-images.githubusercontent.com/7255464/71775081-d31fba00-2f37-11ea-8ab1-9faaad50c9ae.png)

Now that the object being attached is defined, we need too define where on the vehicle it attaches to. Scroll to the top of the page and go to the model (.mode)
![hlmt goto model](https://user-images.githubusercontent.com/7255464/71775158-20505b80-2f39-11ea-812b-91ed2694fb00.png)
Scroll down to Marker Groups and add an index to edit.
![model markers](https://user-images.githubusercontent.com/7255464/71775261-ebdd9f00-2f3a-11ea-935e-f3c4b7991536.png)
Input the name from the earlier "Parent Marker" box into the "Name" box.
Its common that Region Index and Permutation Index is set to -1. Presumably those pertain to the relevant sections in the HLMT tag. Set to -1 to be safe.

Node index chooses where on the vehicle the item goes. An index of zero would attach the gun to "b_pedestal" which is effected by the vehicles suspension. This is not good. Scroll up to Nodes and investigate the different index's. In this case an index of six is chosen to attach the object to "b_chassis" as its not effected by the suspension.

Next input translation values. Numbers 0-4 move the object a far. Use the Poke feature to update the vehicle in-game to help decide exacting translation and rotation values to use. Rotation uses a different system than many are used to. This website is easy to convert Euler angles (XYZ) to Quaternions (IJKW). http://quat.zachbennett.com/
Under "Seats" in truck_cab_large.vehi "Gunner" is selected on the driver seat to enable shooting. The object should now appear in-game.

Result:

![Outcome](https://user-images.githubusercontent.com/7255464/71775281-8fc74a80-2f3b-11ea-85f5-1d7d4390cc78.png)

In the Nodes section of falcon_chin_gun.mode, the falcon chin gun has been scaled up to 1.3 rather than 1.
This results in the bullets spawning too low.
![offset marker](https://user-images.githubusercontent.com/7255464/71775347-8db1bb80-2f3c-11ea-9c44-fac71ef5db2c.png)

Editing the "primary_trigger" marker under Marker Groups allows the heighth adjustment of this through the Translation Z field.
![translation z field](https://user-images.githubusercontent.com/7255464/71775362-044eb900-2f3d-11ea-924c-9a73c9238c9f.png)
