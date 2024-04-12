# Kill Player

When the player comes in contact with an object that has Kill Player behavior attached to it, <mark style="color:purple;">the player is killed and is respawned at the last checkpoint.</mark>&#x20;

This can be used when the player encounters any danger zone or comes in contact with a malicious object.

| Parameters  | Type                                                                                                                                                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened                                                                                                                                                         |
| Effects     | Change in Player or Asset properties, Change in Game Scene Environment, Change in Game Systems, Change in an Asset's Orientation, Create or Elimination existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                                                                                                                                                 |

To add the Update Score behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Update Score behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Update Score.**

You can customize the below-mentioned parameters according to your requirements:

You can customize:

| Parameter                                               | Description                                                                                                                                                |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Play SFX`</mark>             | Choose a short chime to play when the player is killed                                                                                                     |
| <mark style="color:blue;">`Play VFX`</mark>             | Choose a small visual effect to play on the object when the player is killed                                                                               |
| <mark style="color:blue;">`Broadcast On Respawn`</mark> | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player is killed.</code></p> |
