# Kill Player

When the player contacts an object with the Kill Player behavior, the player is killed and respawns at the last checkpoint. This is useful when the player enters a danger zone or interacts with a hazardous object.

| Parameters  | Type                                                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened                                                               |
| Effects     | Change in Player or Asset properties, Elimination existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                                           |

To add the Kill player behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Kill player behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Kill player.**

You can customize the below-mentioned parameters according to your requirements:

You can customize:

| Parameter                                               | Description                                                                                                                                   |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Play SFX`</mark>             | Choose a short chime to play when the player is killed                                                                                        |
| <mark style="color:blue;">`Play VFX`</mark>             | Choose a small visual effect to play on the object when the player is killed                                                                  |
| <mark style="color:blue;">`Broadcast On Respawn`</mark> | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player is killed.</p> |
