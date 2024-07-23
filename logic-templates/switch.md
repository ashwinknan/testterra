# Switch

The switch behavior enables you to regulate the behaviors of an asset, whether it's the one you're interacting with or a different one. You can transmit broadcasts to activate or deactivate behaviors depending on the triggers associated with each action.&#x20;

For instance, suppose a cube possesses a switch behavior. In that case, when the player collides with the cube, an 'on-broadcast' signal is dispatched to the laser, prompting its rotation. Conversely, clicking on the cube sends an 'off-broadcast' signal to the laser, ceasing its rotation.

| Parameters  | Type                                                                                   |
| ----------- | -------------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened, Player exits  |
| Effect      | Generate a Broadcast Signal, Enable an SFX or Particle                                 |
| Type        | Independent                                                                            |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Switch behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Switch behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Switch**.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="313">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Switch On</td><td><p>You can choose the trigger that will turn "on" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object.<br>- When the object is clicked </p></td></tr><tr><td>Sound Effect When On</td><td>Choose a sound effect to play when the switch is turned "on"</td></tr><tr><td>Visual Effect When On</td><td>Choose a visual effect to play when the switch is turned "on"</td></tr><tr><td>Broadcast After On</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "on"</td></tr><tr><td>Switch Off</td><td><p>You can choose the trigger that will turn "off" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object<br>- When the object is clicked</p></td></tr><tr><td>Sound Effect When Off</td><td>Choose a sound effect to play when the switch is turned "off"</td></tr><tr><td>Visual Effect When Off</td><td>Choose a visual effect to play when the switch is turned "off"</td></tr><tr><td>Broadcast After Off</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "off"</td></tr></tbody></table>
