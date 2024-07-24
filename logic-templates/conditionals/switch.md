# Switch

The Switch logic template enables you to regulate the behaviors of an asset, whether it's the one you're interacting with or a different one. You can transmit broadcasts to activate or deactivate behaviors depending on the triggers associated with each action.&#x20;

For instance, suppose a cube possesses a switch logic template. In that case, when the player collides with the cube, an 'on-broadcast' signal is dispatched to the laser, prompting its rotation. Conversely, clicking on the cube sends an 'off-broadcast' signal to the laser, ceasing its rotation.

To add the Switch logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Switch under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="313">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Switch On</td><td><p>You can choose the trigger that will turn "on" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object.<br>- When the object is clicked </p></td></tr><tr><td>Sound Effect When On</td><td>Choose a sound effect to play when the switch is turned "on"</td></tr><tr><td>Visual Effect When On</td><td>Choose a visual effect to play when the switch is turned "on"</td></tr><tr><td>Broadcast After On</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "on"</td></tr><tr><td>Switch Off</td><td><p>You can choose the trigger that will turn "off" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object<br>- When the object is clicked</p></td></tr><tr><td>Sound Effect When Off</td><td>Choose a sound effect to play when the switch is turned "off"</td></tr><tr><td>Visual Effect When Off</td><td>Choose a visual effect to play when the switch is turned "off"</td></tr><tr><td>Broadcast After Off</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "off"</td></tr></tbody></table>

### Accessing the Switch Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [SwitchTemplate](../../coding-using-t/t-logic-template-wrappers.md#switchtemplate)
