# Actions

## Overview

The table below provides an overview of various action logic templates and their descriptions for handling assets in a scene.&#x20;

<table><thead><tr><th width="260">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="actions.md#destroy">Destroy</a></td><td>Destroys the Asset from the scene</td></tr><tr><td><a href="actions.md#set-position">Set Position</a></td><td>Changes the Asset's position</td></tr><tr><td><a href="actions.md#advance-instantiate">Advance Instantiate</a></td><td>Spawns an instance of the player (with advanced settings)</td></tr><tr><td><a href="actions.md#grow-shrink">Grow / Shrink</a></td><td>Increases or decreases the size of the Asset</td></tr><tr><td><a href="actions.md#move">Move</a></td><td>Moves the Asset in a straight line path to a specified new position from its starting point.</td></tr><tr><td><a href="actions.md#rotate">Rotate</a></td><td>Rotates the Asset about a chosen axis</td></tr><tr><td><a href="actions.md#movetoplayer">MoveTo Player</a></td><td>Moves the Asset to the Player</td></tr><tr><td><a href="actions.md#rotate-oscillate">Rotate Oscillate</a></td><td>Oscilates the Asset about a specified axis within a specified rotation about the initial position</td></tr><tr><td><a href="actions.md#basic-instantiate">Basic Instantiate</a></td><td>Spawns an instance of the player</td></tr><tr><td><a href="actions.md#bump">Bump</a></td><td>Bounce back when you run into it</td></tr></tbody></table>

## List of all Action Logic Components

### Destroy

The Destroy logic template is used when you want to remove or destroy assets from the game scene on a certain trigger. The asset with this logic template are destroyed without any trace of them being there.

This logic template is very similar to the Collectable behaviour, the only difference being that the Collectable contributes to a score group and this does not. In both logic templates, the asset disappears after the trigger.

To add the Destroy logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Destroy under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="288">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the asset.<br>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Destroy After</td><td>The time in seconds after which the asset disappears from the scene.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [DestroyTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#destroytemplate)

### Set Position

The Set Position logic template enables you to specify the position of an asset.

To add the Set Position logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Set Position under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="239">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Set Position on</td><td><p>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Target</td><td>Specify the target destination position either by recording or entering the target coordinates in the fields X, Y and Z.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play on execution</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play on execution</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [SetPositionTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#setpositiontemplate)

### Advance Instantiate

The advanced instantiation logic template allows you to spawn asset instances in the game scene during runtime.

To add the Advance Instantiate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Advance Instantiate under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="251">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the asset.<br>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Destroy After</td><td>The time in seconds after which the asset disappears from the scene.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.

### Grow / Shrink

The Grow or Shrink behavior can be used to change the size of an object. Various types of triggers can be used to grow or shrink the object.

To add the Grow/Shrink logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Grow/Shrink under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Grow When</td><td>You can choose the trigger on which the object will start growing.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></td></tr><tr><td>Scale by</td><td>You can specify the scale by which an object's size will grow or shrink</td></tr><tr><td>Speed</td><td>You can define the speed by which object will grow or shrink</td></tr><tr><td>Repeat </td><td>You can define the number of time you want the behaviour to be executed </td></tr><tr><td>Repeat forever </td><td>You can set the change in size behaviour to forever by checking this checkbox.</td></tr><tr><td>Pause for</td><td>The duration of the pause between each cycle of behaviour execution can be adjusted here</td></tr><tr><td>Repeat type </td><td>You can use this option to select the type of motion while change<br>There are two types motion the behaviour supports at the moment <br>1. Ping Pong<br>2. Same Direction </td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when object starts moving</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when object starts moving</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [GrowTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#growtemplate)

### Move

The Move behavior lets objects travel in a straight line between two points. They can move in any direction, switch between two points, and trigger other actions. For nonlinear paths with multiple points, use the MultiPoint Move template instead of move.

To add the Move logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Move under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Move When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</p></td></tr><tr><td>Speed</td><td>You can define the speed of the object</td></tr><tr><td>Loop-able</td><td>This allows you to loop the movement of the object. It appears as if it is oscillating between 2 different points.</td></tr><tr><td>Interval</td><td>Intervals add a delay between the back-and-forth movement of the object during the loop.</td></tr><tr><td>Move By</td><td>You can define how many units and in what axis the object will move</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr><tr><td>Broadcast on End</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Stop When</td><td>You can choose the trigger to stop the movement<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Resume When</td><td>You can choose the trigger to resume the movement<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [MoveTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#movetemplate)

### Rotate

When the Rotate logic template is applied to objects, they begin to rotate about their axis upon a specific trigger.

To add the Rotate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Rotate under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Rotate When</td><td>You can choose the trigger on which the object will start rotating.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></td></tr><tr><td>Rotation Axis</td><td>You can choose the axis in which the object will rotate (X,Y,Z axis)</td></tr><tr><td>Speed</td><td>You can define the rotation speed of the object</td></tr><tr><td>Direction</td><td>You can define the direction of motion either clockwise or anticlockwise</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when object starts moving</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when object starts moving</td></tr><tr><td>Stop When</td><td>You can choose which trigger will stop the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr><tr><td>Restart When</td><td>You can choose which trigger will restart the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [RotateTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#rotatetemplate)

### MoveToPlayer

Objects with the MoveToPlayer behavior will leave their designated location and move towards the player.  They track the player's movement and follow in the same direction. Multiple triggers can activate this behavior as needed.

To add the Move To Player logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Move To Player under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="306">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>MoveToPlayerWhen</td><td>You can choose the trigger to activate the behaviour<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>MoveSpeed</td><td>You can fix the speed for object movement</td></tr><tr><td>Offset</td><td>Specifying offset value ensures that the object will move a specific number of units in the given axis. It won't follow you but will relocate to a different location on triggering.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Cancel On</td><td>You can choose when to stop the movement of the object.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.</td></tr><tr><td>Cancel Type</td><td>You can choose what happens to the object once it stops moving. <br>- It can relocate back to its original position.<br>- It can stop at the current position.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object comes in contact with you.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [MoveToPlayerTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#movetoplayertemplate)

### Rotate Oscillate

When the Rotate Oscillate logic template is applied to objects, they begin to oscillate around their axis at a defined angle and speed upon a specific trigger.

To add the Rotate Oscillate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Rotate Oscillate under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Rotate On</td><td>You can choose the trigger on which the object will start rotating.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></td></tr><tr><td>Axis</td><td>You can choose the axis about which the object will oscillate (X,Y,Z axis)</td></tr><tr><td>Speed</td><td>You can define the rotation speed of the object</td></tr><tr><td>Degrees</td><td>define the angle at which the object would oscillate </td></tr><tr><td>Direction</td><td>You can define the direction of motion either clockwise or anticlockwise</td></tr><tr><td>Repeat</td><td>You can define the number of time you want the oscillation to occur</td></tr><tr><td>Repeat Forever </td><td>You can set the oscillation to forever by checking this checkbox.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when object starts moving</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when object starts moving</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Stop On</td><td>You can choose which trigger will stop the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr><tr><td>Restart On</td><td>You can choose which trigger will restart the movement. Those can be:<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [RotateOscillateTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#rotateoscillatetemplate)

### Basic Instantiate

The Basic Instantiate behavior facilitates the dynamic spawning of identical objects in various locations during gameplay. It allows for controlled timing and quantity of object spawns.

You can determine where objects appear in the game scene by specifying a range of X, Y, and Z coordinates or by randomizing their location within a designated area. With the first method, you have precise control over the specific combinations of coordinates where objects will spawn. Alternatively, using the random allocation option, you can define an area using the record feature, allowing objects to appear randomly within that area during gameplay.

To add the Basic Instantiate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Basic Instantiate under the header "Action".
3. Drag and drop it onto the desired asset.&#x20;

You can edit the following parameters of this template directly through the scene editor interface:

| Parameters      | Description                                                                                                                                                                                                                                                                                                                                                   |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Instantiate On  | <p>You can choose the start event from the dropdown to activate the behaviour<br>- After a broadcast message has been received by the asset<br>- When the game starts</p>                                                                                                                                                                                     |
| Repeat On Event | If you check this box, the asset will appear only once in the scene                                                                                                                                                                                                                                                                                           |
| No of instance  | You can set how many assets will respawn at a time                                                                                                                                                                                                                                                                                                            |
| Position        | <p>You can choose where you want the assets to respawn using the dropdown. You can choose from:<br>- Locator: Objects will spawn at specific coordinates. You can set the coordinates by clicking the "+" sign below the location positions.<br>- Random in area: Objects will spawn at random coordinates. You can define the area using record feature.</p> |
| Randomise       | This parameter is specifically for locators. It causes objects to spawn at the specified coordinates, but the order of the coordinates will be randomized, disregarding the order in which they were defined.                                                                                                                                                 |
| Play SFX        | Choose a sound effect to play every time the asset spawns                                                                                                                                                                                                                                                                                                     |
| Play VFX        | Choose a visual effect to play every time the asset spawns                                                                                                                                                                                                                                                                                                    |
| Broadcast       | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the assets spawn.</p>                                                                                                                                                                                                                     |

There are currently no available T# wrappers to access this template.&#x20;

### Bump

The Bump logic template 'bumps' and pushes any asset that contacts the asset it is applied to.

To add the Bump logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Bump under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="452">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Force</td><td>Enter the force to be applied</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Type</td><td>Choose from a dropdown whether the bump needs to be a Reflect or a Deflect</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.
