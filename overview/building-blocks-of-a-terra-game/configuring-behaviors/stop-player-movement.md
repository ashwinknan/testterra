# Stop Player movement

When a player comes into contact with an asset that has the StopPlayerMovement behavior applied, the player's motion in the game environment is halted. This behavior locks the player in their current position.

| Parameters  | Type                                                                                |
| ----------- | ----------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Generate a Broadcast Signal, Enable an SFX or Particle                              |
| Type        | dependent                                                                           |

To add the Stop player movement behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Stop player movement behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Stop player movement.**

You can customize the below-mentioned parameters according to your requirements:

You can customize these parameters:

<table><thead><tr><th width="246">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the player stops moving.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the player stops moving.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player stops moving again.</td></tr></tbody></table>



