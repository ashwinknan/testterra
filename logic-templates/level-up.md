# Level Up

Level up behaviour is used to upgrade diffrent in-game assets based on the the upgrade paths of objects defined using the [Level Maper](../conceptual-guides/setting-up-game-systems.md) game system.

| Parameters  | Type                                                                                                                |
| ----------- | ------------------------------------------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened                                             |
| Effects     | Change in Player or Asset properties, Change in game system, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                         |

To add the Level up behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Level up behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Level up.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Level up when</td><td>You can choose the trigger to activate the behaviour <br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr><tr><td>Manager group</td><td>Helps to choose the score group</td></tr><tr><td>Broadcast Success</td><td></td></tr><tr><td>Broadcast fails </td><td></td></tr><tr><td>Execute </td><td>Number of times behaviour need to be excuted </td></tr></tbody></table>

