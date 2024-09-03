# Mechanics

## Overview

This table outlines various mechanics that are commonly used in games and  enable different interactions and behaviors for game objects, such as being collected by the player, creating enhancements, applying forces, enabling rotations, and more.

<table><thead><tr><th width="255">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="mechanics.md#collectable">Collectable</a></td><td>Enables an object to be collected by the player and update the game score. Used in Power-ups. </td></tr><tr><td><a href="mechanics.md#teleport-player">Teleport Player</a></td><td>Instantly spawns the Player in a new specified position</td></tr><tr><td><a href="mechanics.md#jump-pad">Jump Pad</a></td><td>Creates a jump enhancement for the player upon contact</td></tr><tr><td><a href="mechanics.md#carryable">Carryable</a></td><td>Enables an Asset to be carried by the Player. The Asset will now move with the Player</td></tr><tr><td><a href="mechanics.md#deposit">Deposit</a></td><td>Enables the Player to transfer the Carriable Asset and deposit it to a new Asset which is a storage</td></tr><tr><td><a href="mechanics.md#modify-carryable">Modify Carryable</a></td><td>Modifies the number of carryables you have</td></tr><tr><td><a href="mechanics.md#kill-player">Kill Player</a></td><td>Respawns the player to the start of the level</td></tr><tr><td><a href="mechanics.md#hinge-joint">Hinge Joint</a></td><td>Enables assets to rotate about a defined hinge like a dore</td></tr><tr><td><a href="mechanics.md#explosive-force">Explosive Force</a></td><td>Applies a force / impulse on a radius</td></tr><tr><td><a href="mechanics.md#add-force">Add Force</a></td><td>Applies a force on an object and allows it to follow physics </td></tr><tr><td><a href="mechanics.md#treadmill">Treadmill</a></td><td>Enables treadmill-like motion on contact</td></tr><tr><td><a href="mechanics.md#multi-point-move">Multipoint Move</a></td><td>Shifts the Asset from its starting spot through a path of straight or curved points as needed.</td></tr><tr><td><a href="mechanics.md#attach-object">Attach Object</a></td><td>Parents an object to another object</td></tr></tbody></table>

## List of all Mechanics Logic Template Components

### Collectable

A Collectible is a logic template added to an asset in a game that can be collected to increase score or to achieve another goal.

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Collectable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Collectable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter               | Description                                                                                                                                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Collect When            | <p></p><p>Choose when the item is “collected”:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Sound Effect on Start   | Choose a short chime to play when item is collected                                                                                                                                                                   |
| Visual Effect on Start  | Choose a small visual effect to play when item is collected                                                                                                                                                           |
| Score Group             | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                          |
| Update Score By         | <p>Enter a numerical score value to update when collected.<br>✨ Note: to reduce a score when collected, enter a negative value!</p>                                                                                   |
| IsMultiLevel            | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                     |
| Broadcast On Collection | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                         |

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [CollectableTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#collectabletemplate)

### Teleport Player

The Teleport Player logic template can be used to teleport the player from one location to another in response to a specified trigger.

To add the Teleport Player logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Teleport Player under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="367">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Teleport When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</p></td></tr><tr><td>Teleport </td><td>You can choose the coordinates where you want the player to be teleported.</td></tr><tr><td>Loop-able</td><td>This allows you to loop the movement of the object. It appears as if it is oscillating between 2 different points.</td></tr><tr><td>Interval</td><td>Intervals add a delay between the back-and-forth movement of the object during the loop.</td></tr><tr><td>Move By</td><td>You can define how many units and in what axis the object will move</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving..</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [TeleportTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#teleporttemplate)

### Jump Pad

The Jump Pad boosts the player's jump height when attached to an asset. Upon touching an object with the Jump Pad logic template, the player's jump is elevated. After the jump action, the jump height is restored to the initial value.

To add the Jump Pad logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Jump Pad under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameters     | Description                                                                                                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX       | Choose a sound effect to play when the player jumps                                                                                                                           |
| Play VFX       | Choose a visual effect to play when the player jumps                                                                                                                          |
| Jump Force     | Define the multiplier by which the existing jump height will be multiplied for that instance                                                                                  |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player jumps at an increased height.</code></p> |

{% hint style="info" %}
Your Jump Height should ideally be greater than 2 for the Jump Pad to work. Small jump height values will not lead to an increased jump height. You can find Jump Height in the Player Controller Drawer. Eg: A jump Height of 0.1 with a Jump Force of 10 will change the total jump height to 0.01 which is lower than the initial height.
{% endhint %}

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [JumpPadTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#jumppadtemplate)

### Carryable

A carriable is a logic template that, when attached to a game asset, enables the player to carry it.&#x20;

To add the Carryable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Carryable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

To add the Carryable behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Carriable behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose Carriable.

You can customize the below-mentioned parameters according to your requirements:

| Parameter          | Description                                                                                                                                                                                                                             |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Group              | You can group the carryables in different categories using this dropdown.                                                                                                                                                               |
| Carry on           | <p></p><p>Choose when the item is “carried”, using the dropdown:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Play SFX           | Choose a short chime to play when item is collected                                                                                                                                                                                     |
| Play VFX           | Choose a small visual effect to play when item is collected                                                                                                                                                                             |
| Size of carriable  |                                                                                                                                                                                                                                         |
| Score Group        | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                                            |
| Lerp               |                                                                                                                                                                                                                                         |
| Lerp Time          |                                                                                                                                                                                                                                         |
| Score              | Enter a numerical score value to update when collected.                                                                                                                                                                                 |
| IsMultiLevel       | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                                       |
| Broadcast          | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                           |

Configure the player setting for the carryable behaviour:

1. Navigate to the essentials tab from the builder menu.
2. Select the PlayerControllerDrawer from the builder panel. this would open the inspector panel
3. Navigate to carryable properties section in the inspector pannel.

| Parameter             | Description                                                                  |
| --------------------- | ---------------------------------------------------------------------------- |
| Locator for cariable  | set the position of the carryable on the player using the record button      |
| Limit                 | the number of carryables can be limited using this field                     |
| Stack offset          | Using this option you can set the position of the carrible around the player |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Deposit

The deposit logic template when applied to an asset, allows it to collect a specified carryable. The deposit logic template cannot work independently when there is no carryable in the scene

To add the Deposit logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Deposit under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter              | Description                                                                                                                                                                                                                                                                 |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Deposit when           | <p></p><p>Choose when the item is “Deposited”, using the dropdown:</p><ul><li>when player touches</li><li>when other object touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Take Resource          | Selects the asset group which serves as the currency                                                                                                                                                                                                                        |
| Persistent             | Checking this box                                                                                                                                                                                                                                                           |
| Play SFX               | Choose a short chime to play when item is collected                                                                                                                                                                                                                         |
| Play VFX               | Choose a small visual effect to play when item is collected                                                                                                                                                                                                                 |
| Lerp                   |                                                                                                                                                                                                                                                                             |
| Lerp Time              |                                                                                                                                                                                                                                                                             |
| Cost type              |                                                                                                                                                                                                                                                                             |
| Size of carriable      |                                                                                                                                                                                                                                                                             |
| Score Group            | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                                                                                |
| Deposit rate           | You can set the rate at which the carriable will get deposited.                                                                                                                                                                                                             |
| Of Amount              |                                                                                                                                                                                                                                                                             |
| Score                  | Enter a numerical score value to update when collected.                                                                                                                                                                                                                     |
| IsMultiLevel           | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                                                                           |
| limit                  |                                                                                                                                                                                                                                                                             |
| Show Progress          |                                                                                                                                                                                                                                                                             |
| Is Ascending           |                                                                                                                                                                                                                                                                             |
| Broadcast              | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                                                               |
| Broadcast stack empty  |                                                                                                                                                                                                                                                                             |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Kill Player

When the player contacts an object with the Kill Player behavior, the player is killed and respawns at the last checkpoint. This is useful when the player enters a danger zone or interacts with a hazardous object.

To add the Kill Player logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Kill Player under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                               | Description                                                                                                                                   |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Play SFX`</mark>             | Choose a short chime to play when the player is killed                                                                                        |
| <mark style="color:blue;">`Play VFX`</mark>             | Choose a small visual effect to play on the object when the player is killed                                                                  |
| <mark style="color:blue;">`Broadcast On Respawn`</mark> | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player is killed.</p> |

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [KillPlayerTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#killplayertemplate)

### Multi-Point Move

Multi-Point Move is a logic template that allows you to instruct an Asset to follow a path made up of several points once its Start Event occurs. This path can be straight lines or curves between the points, giving you many choices for how the Asset moves.

The Asset can automatically turn to make sure a specific side always points towards the path, just like how our face turns to the direction we are moving.

To add the Multi-Point Move logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Multi-Point Move under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="204">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Move On</td><td>This is a dropdown from where you need select any one of the following Start Events for Interpolate Points to begin executing: <br> <br>1. When the behavior  when the game starts: Select "Game Start"<br>2. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>3. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>4. When the player touches the currently selected Asset: Select "Player Touchers"<br>5. When the Asset is clicked: Select "On Click" </td></tr><tr><td>Points</td><td>This helps you specify the coordinates of the multiple points through which the Asset will move in a path. Click the + button to add points and - button to remove an existing point</td></tr><tr><td>Speed</td><td>This is an input field where you can enter a number that represents the speed of Asset movement</td></tr><tr><td>Turn To Points</td><td>This toggle button ensures that only one side of the Asset always faces forward. When activated, it adjusts the Asset's orientation to maintain this specific direction during movement.</td></tr><tr><td>Delay at Point</td><td>This field lets you set a delay in seconds. During this delay, the Asset will not move. After the time passes, it will start moving again.</td></tr><tr><td>Loop</td><td>This toggle button, when activated, enables the movement to repeat continuously</td></tr><tr><td>Is Curve</td><td>This toggle button alters the Asset's trajectory between points to follow a curved path instead of a linear one.</td></tr><tr><td>Interpolate Types</td><td><p></p><p>This dropdown lets you pick how the object moves:</p><ul><li>For forward movement only, select <strong>One Direction</strong></li><li>For back-and-forth movement, select <strong>Ping Pong</strong></li></ul></td></tr><tr><td>Broadcast Type &#x26; Broadcast Signal</td><td><p>The Broadcast Signal option allows you to create a game signal that other can act as the Start Event for other behavior blocks to execute. You can choose "Game Win", "Game Lose", or create your own custom signal. For a custom signal, you must select "Custom" from the dropdown and enter a name in the input field.<br><br>The Broadcast Type dropdown lets you specify when the broadcast signal will be sent. There are three options to choose from:</p><ul><li>If you want no broadcast to be sent, Select Never</li><li>If you want to send a broadcast after finishing one whole movement from start to end, select End </li><li>If you want to send the broadcast signal every time the object pauses , select At Every Pause</li></ul></td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper- [MoveBetweenPointsTemplate ](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#movebetweenpointstemplate)

### Modify Carryable

The Modify Carryable Logic Template allows you to modify the number of carryables carried. &#x20;

To add the Modify Carryable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Modify Carryable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Modify When`</mark>    | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br><br>1. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Play VFX`</mark>       | Choose a small visual effect to play on the execution                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Play SFX`</mark>       | Choose a sound effect to play on the execution                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Haptics`</mark>        | Select Haptics from a dropdown                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Modifier Group`</mark> | Select a which carryable needs to be modified                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <mark style="color:blue;">`Execute Always`</mark> | Toggle to Specify if this always needs to be executed                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Modifier`</mark>       | Select a modifier to the carriable - Add, Subtract, Multiply                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| <mark style="color:blue;">`Modify By`</mark>      | Amount / Value to be modified by                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Hinge Joint

The Hinge Joint Logic Template allows you to make an asset rotate around a hinge joint to mimic the movement of a door.  &#x20;

To add the Hinge Joint logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Hinge Joint under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                        | Description                                                                            |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Axis`</mark>          | Helps specify the axis of rotation                                                     |
| <mark style="color:blue;">`Anchor`</mark>        | Specify the anchor point around which hinge movement must happen                       |
| <mark style="color:blue;">`Can Spin Back`</mark> | Toggle to specify if the object can spin back to original position after the rotation. |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Explosive Force

The Explosive Force Logic Template allows the attached object to exert a sudden explosive force or impulse on nearby objects within a certain radius.

To add the Explosive Force logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Explosive Force under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Explode When`</mark> | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Force`</mark>        | Specify the value of the force to be applied                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <mark style="color:blue;">`Radius`</mark>       | Specify the radius where the force is felt                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <mark style="color:blue;">`Explode SFX`</mark>  | Choose a short chime to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <mark style="color:blue;">`Explode VFX`</mark>  | Choose a small visual effect to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Broadcast`</mark>    | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after execution</p>                                                                                                                                                                                                                                                                                                                                                             |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Add Force

The Add Force Logic Template allows you to apply a force on an asset and enable it to act according to the laws of physics.&#x20;

To add the Add Force logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Add Force under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Add Force When`</mark> | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Force`</mark>          | Specify the value of the force to be applied                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <mark style="color:blue;">`Repeat Mode`</mark>    | Dropdown to select the nature of repetition if any - Single, Repetitive, Periodic                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Period`</mark>         | If periodic, specify the period                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| <mark style="color:blue;">`Play SFX`</mark>       | Choose a short chime to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <mark style="color:blue;">`Play VFX`</mark>       | Choose a small visual effect to play on execution                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| <mark style="color:blue;">`Broadcast`</mark>      | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after execution</p>                                                                                                                                                                                                                                                                                                                                                             |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Treadmill

The Treadmill Logic Template simulates treadmill movement for objects or the Player upon touch.

To add the Treadmill logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Treadmill under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="357">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Treadmill When</code></mark></td><td>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When the behavior  when the game starts: Select "Game Start"<br>2. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>3. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>4. When the player touches the currently selected Asset: Select "Player Touchers"<br>5. When the Asset is clicked: Select "On Click" </td></tr><tr><td><mark style="color:blue;"><code>Play SFX</code></mark></td><td>Choose a short chime to play when the player starts the treadmill</td></tr><tr><td><mark style="color:blue;"><code>Play VFX</code></mark></td><td>Choose a small visual effect to play on the object when the player starts the treadmill</td></tr><tr><td><mark style="color:blue;"><code>Treading Speed</code></mark></td><td>Specify the speed of the treadmill</td></tr><tr><td><mark style="color:blue;"><code>Treading Direction</code></mark></td><td>Specify the direction of movement of the treadmill</td></tr><tr><td><mark style="color:blue;"><code>broadcastData</code></mark></td><td>Specify a broadcast signal to be generated after execution</td></tr></tbody></table>

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.

### Attach Object

The Attach Object Logic Template allows you to attach one object to another, making the new object a child of the original object.

To add the Attach Object logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Attach Object under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`AttachOn`</mark>     | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When the behavior  when the game starts: Select "Game Start"<br>2. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>3. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>4. When the player touches the currently selected Asset: Select "Player Touchers"<br>5. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Attach_To`</mark>    | Select from the dropdown whether you want to attach the object to the Player or A Game Object.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| <mark style="color:blue;">`Attach To`</mark>    | <p>If you chose GameObject, drag and drop the game object references from the layers here.<br><br>This will be set to None if you selected Player on Attach_To</p>                                                                                                                                                                                                                                                                                                                                                                                                |
| <mark style="color:blue;">`KeepWorldPos`</mark> | Toggle to indicate if you want to keep the world position of the object                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <mark style="color:blue;">`Offset`</mark>       | Indicate the offset between the parent and the child                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.
