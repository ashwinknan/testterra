# Grow / Shrink

The Grow or Shrink behavior can be used to change the size of an object. Various types of triggers can be used to grow or shrink the object.

To add the Grow/Shrink logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Grow/Shrink under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Grow When</td><td>You can choose the trigger on which the object will start growing.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></td></tr><tr><td>Scale by</td><td>You can specify the scale by which an object's size will grow or shrink</td></tr><tr><td>Speed</td><td>You can define the speed by which object will grow or shrink</td></tr><tr><td>Repeat </td><td>You can define the number of time you want the behaviour to be executed </td></tr><tr><td>Repeat forever </td><td>You can set the change in size behaviour to forever by checking this checkbox.</td></tr><tr><td>Pause for</td><td>The duration of the pause between each cycle of behaviour execution can be adjusted here</td></tr><tr><td>Repeat type </td><td>You can use this option to select the type of motion while change<br>There are two types motion the behaviour supports at the moment <br>1. Ping Pong<br>2. Same Direction </td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when object starts moving</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when object starts moving</td></tr></tbody></table>

### Accessing the Grow/Shrink Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [GrowTemplate](../../coding-using-t/t-logic-template-wrappers.md#growtemplate)

