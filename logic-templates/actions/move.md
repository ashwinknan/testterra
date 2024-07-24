# Move

The Move behaviour can be attached to objects to give them mobility. Objects can move along all three axes, oscillate between two points, and send broadcasts to trigger additional behaviour.

To add the Move logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Move under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Move When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</p></td></tr><tr><td>Speed</td><td>You can define the speed of the object</td></tr><tr><td>Loop-able</td><td>This allows you to loop the movement of the object. It appears as if it is oscillating between 2 different points.</td></tr><tr><td>Interval</td><td>Intervals add a delay between the back-and-forth movement of the object during the loop.</td></tr><tr><td>Move By</td><td>You can define how many units and in what axis the object will move</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr><tr><td>Broadcast on End</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Stop When</td><td>You can choose the trigger to stop the movement<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Resume When</td><td>You can choose the trigger to resume the movement<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object.</td></tr></tbody></table>

### Accessing the Move Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [MoveTemplate](../../coding-using-t/t-logic-template-wrappers.md#movetemplate)
