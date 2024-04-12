# Stop Move

The Stop Move behavior can be attached to objects to halt their movement.

| Parameters  | Type                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |
| Start Event | other object touches, mouse clicked, broadcast listened                                  |
| Effects     | Change in an Asset's Orientation, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | dependent                                                                                |

To add the Stop Move behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Stop Move behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Stop Move.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Stop When</td><td>You can choose the trigger to activate the behaviour <br>- After a broadcast message has been received by the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object stops</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object stops </td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr></tbody></table>
