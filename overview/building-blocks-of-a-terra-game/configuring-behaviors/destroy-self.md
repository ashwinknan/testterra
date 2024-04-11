# Destroy Self

The destroy self behaviour is used when you want to remove or destroy assets from the game scene on a certain trigger. The asset with this behaviour are destroyed without any trace of them being there.

This behaviour is very similar to the Collectable behaviour, the only difference being that the Collectable contributes to a score group and this does not. In both behaviour, the asset disappears after the trigger.

| Parameters  | Type                                                                                                                                                |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | Interaction based triggers(For example: player collides, mouse clicked, other assets collides), Event based trigger (Broadcast listen, game starts) |
| Effect      | Visual or auditory effects (like - SFX,VFX), Elimination game object, Change in game systems(Win or loose), Trigger another behavior                |
| Type        | Independent                                                                                                                                         |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Destroy Self behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Destroy Self behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Destroy Self.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="288">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the asset.<br>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Destroy After</td><td>The time in seconds after which the asset disappears from the scene.</td></tr></tbody></table>

