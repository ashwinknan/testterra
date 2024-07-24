# Rotate Oscillate

When the Rotate Oscillate logic template is applied to objects, they begin to oscillate around their axis at a defined angle and speed upon a specific trigger.

To add the Rotate Oscillate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Rotate Oscillate under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Rotate On</td><td>You can choose the trigger on which the object will start rotating.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></td></tr><tr><td>Axis</td><td>You can choose the axis about which the object will oscillate (X,Y,Z axis)</td></tr><tr><td>Speed</td><td>You can define the rotation speed of the object</td></tr><tr><td>Degrees</td><td>define the angle at which the object would oscillate </td></tr><tr><td>Direction</td><td>You can define the direction of motion either clockwise or anticlockwise</td></tr><tr><td>Repeat</td><td>You can define the number of time you want the oscillation to occur</td></tr><tr><td>Repeat Forever </td><td>You can set the oscillation to forever by checking this checkbox.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when object starts moving</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when object starts moving</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Stop On</td><td>You can choose which trigger will stop the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr><tr><td>Restart On</td><td>You can choose which trigger will restart the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr></tbody></table>

### Accessing the Rotate Oscillate Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [RotateOscillateTemplate](../../coding-using-t/t-logic-template-wrappers.md#rotateoscillatetemplate)
