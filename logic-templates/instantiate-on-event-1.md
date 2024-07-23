# Instantiate on event

The Instantiate on event behavior facilitates the dynamic spawning of identical objects in various locations during gameplay. It allows for controlled timing and quantity of object spawns.

You can determine where objects appear in the game scene by specifying a range of X, Y, and Z coordinates or by randomizing their location within a designated area. With the first method, you have precise control over the specific combinations of coordinates where objects will spawn. Alternatively, using the random allocation option, you can define an area using the record feature, allowing objects to appear randomly within that area during gameplay.

| Parameters   | Type                                                                               |
| ------------ | ---------------------------------------------------------------------------------- |
| Start Event  | Broadcast listen, game starts                                                      |
| Effect       | Creates Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type         | Independent                                                                        |

One or multiple triggers can be created, resulting in one or multiple outcomes.

\
To add the Instantiate behavior to an asset, follow these steps:

{% embed url="https://www.loom.com/share/151848e0501949b2b72dd42969d93343?sid=9ae333cc-1a8d-4ac6-b363-b5c8d1a4fe29" %}

1. Select the asset you wish to apply the Instantiate behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Instantiate.**

You can customize the below-mentioned parameters according to your requirements:

| Parameters      | Description                                                                                                                                                                                                                                                                                                                                                   |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Instantiate On  | <p>You can choose the start event from the dropdown to activate the behaviour<br>- After a broadcast message has been received by the asset<br>- When the game starts</p>                                                                                                                                                                                     |
| Repeat On Event | If you check this box, the asset will appear only once in the scene                                                                                                                                                                                                                                                                                           |
| No of instance  | You can set how many assets will respawn at a time                                                                                                                                                                                                                                                                                                            |
| Position        | <p>You can choose where you want the assets to respawn using the dropdown. You can choose from:<br>- Locator: Objects will spawn at specific coordinates. You can set the coordinates by clicking the "+" sign below the location positions.<br>- Random in area: Objects will spawn at random coordinates. You can define the area using record feature.</p> |
| Randomise       | This parameter is specifically for locators. It causes objects to spawn at the specified coordinates, but the order of the coordinates will be randomized, disregarding the order in which they were defined.                                                                                                                                                 |
| Play SFX        | Choose a sound effect to play every time the asset spawns                                                                                                                                                                                                                                                                                                     |
| Play VFX        | Choose a visual effect to play every time the asset spawns                                                                                                                                                                                                                                                                                                    |
| Broadcast       | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the assets spawn.</p>                                                                                                                                                                                                                     |

