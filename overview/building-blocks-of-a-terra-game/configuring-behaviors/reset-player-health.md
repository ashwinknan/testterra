# Reset Player Health

When a player interacts with an object tagged with the Reset Player Health behavior, the player's health is fully restored. This can be useful when a player respawns after dying, enters a safe zone, collects healing items, or faces similar situations.

| Parameters  | Type                                                                                         |
| ----------- | -------------------------------------------------------------------------------------------- |
| Start Event | player touches, mouse clicked, broadcast listened                                            |
| Effects     | Change in Player or Asset properties, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                  |

To add the Reset Player Health behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Reset Player Health behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Reset Player Health.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When the object is clicked.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health is reset</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health is reset</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when health is restored.</td></tr></tbody></table>
