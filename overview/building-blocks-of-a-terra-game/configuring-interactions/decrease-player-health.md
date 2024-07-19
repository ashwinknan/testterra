# Decrease Player Health

In games, lowering the player's health as a result of certain interactions is a common mechanic. The Decrease Player Health behavior reduces the player's health when specific triggers are activated, such as:

* Colliding with obstacles.
* Indirect factors like a game timer nearing its limit, which pushes the player to complete objectives quickly or seek methods to restore health.

| Parameters  | Type                                                                                |
| ----------- | ----------------------------------------------------------------------------------- |
| Start Event | player touches, broadcast listened                                                  |
| Effects     | Change in Player properties, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                         |

To add the Decrease Player Health behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Decrease Player Health behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Decrease Player Health.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="291">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.</td></tr><tr><td>By Point</td><td>The player's health will decrease by the defined amount when the behaviour is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health decreases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health decreases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent everytime the player health decreases.</td></tr></tbody></table>
