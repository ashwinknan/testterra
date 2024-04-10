# Switch

The switch behavior enables you to regulate the behaviors of an asset, whether it's the one you're interacting with or a different one. You can transmit broadcasts to activate or deactivate behaviors depending on the triggers associated with each action.&#x20;

For instance, suppose a cube possesses a switch behavior. In that case, when the player collides with the cube, an 'on-broadcast' signal is dispatched to the laser, prompting its rotation. Conversely, clicking on the cube sends an 'off-broadcast' signal to the laser, ceasing its rotation.

| Parameters  | Type                                                                                                                                                  |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Trigger     | Interaction based triggers(For example: Player exits, player collides, mouse clicked, other assets collides,), Event based trigger (Broadcast listen) |
| Outcome     | Visual or auditory effects (like - SFX,VFX),  Trigger another behavior                                                                                |
| Type        | Independent                                                                                                                                           |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Switch behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Switch behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Switch**.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="313">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Switch On</td><td><p>You can choose the trigger that will turn "on" the switch:</p><p>- When a different object touches the <mark style="color:yellow;">object</mark><br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br><mark style="color:yellow;">-</mark> When the player <mark style="color:yellow;">exits</mark><br>- When the player collides with the <mark style="color:yellow;">object</mark><br>- When the object is <mark style="color:yellow;">clicked</mark></p></td></tr><tr><td>Sound Effect When On</td><td>Choose a sound effect to play when the switch is turned "on"</td></tr><tr><td>Visual Effect When On</td><td>Choose a visual effect to play when the switch is turned "on"</td></tr><tr><td>Broadcast After On</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when switch is turned "on"</code></td></tr><tr><td>Switch Off</td><td><p>You can choose the trigger that will turn "off" the switch:</p><p>- When a different object touches the <mark style="color:yellow;">object</mark><br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br><mark style="color:yellow;">-</mark> When the player <mark style="color:yellow;">exits</mark><br>- When the player collides with the <mark style="color:yellow;">object</mark><br>- When the object is <mark style="color:yellow;">clicked</mark></p></td></tr><tr><td>Sound Effect When Off</td><td>Choose a sound effect to play when the switch is turned "off"</td></tr><tr><td>Visual Effect When Off</td><td>Choose a visual effect to play when the switch is turned "off"</td></tr><tr><td>Broadcast After Off</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when switch is turned "off"</code></td></tr></tbody></table>
