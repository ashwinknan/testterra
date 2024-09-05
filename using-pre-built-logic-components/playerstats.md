# PlayerStats

## Overview

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="playerstats.md#update-score">Update Score</a></td><td>Updates a specific score group to a new specified value</td></tr><tr><td><a href="playerstats.md#reset-score">Reset Score</a></td><td>Resets the specified score group to zero</td></tr><tr><td><a href="playerstats.md#increase-player-hp">Increase Player HP</a></td><td>Increases the player Health value by the specific amount</td></tr><tr><td><a href="playerstats.md#decrease-player-hp">Decrease Player HP</a></td><td>Decreases the player Health value by a specific amount</td></tr><tr><td><a href="playerstats.md#reset-player-health">Reset Player Health</a></td><td>Resets the player Health value to zero</td></tr><tr><td><a href="playerstats.md#level-up">Level Up</a></td><td>Guides the Level Mapper on how to increase a property's level to the next tier.</td></tr><tr><td><a href="playerstats.md#update-magnet">Update Magnet</a></td><td>Changes the magnet range for the player's collection</td></tr><tr><td><a href="playerstats.md#stop-player-template">Stop Player Movement</a></td><td>Stops or starts the player movements</td></tr><tr><td><a href="playerstats.md#change-player-speed">Change Player Speed</a></td><td>Changes the speed of movement of the player</td></tr></tbody></table>

## List of PlayerStats Logic Template Components

### Update Score

You may want to enhance the gameplay experience by adjusting the game [score ](../conceptual-guides/adding-global-logic-components.md#score)when specific conditions are met. For instance:

* Update the score when the player collects items such as coins, gems, or power-ups. This promotes exploration and rewards the player's curiosity.
* Increase the score upon completing a level or reaching a milestone, such as finishing a race track or solving a puzzle.
* Award points for unique or challenging achievements outside the normal gameplay loop, such as discovering hidden areas.

You do this using the Update Score logic template component. To add the Update Score logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Update Score under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for updating the score. There are four triggers allowed:<br>Player Touches- Updates the score when the player touches the selected object<br>Other Object Touches - Updates the score when another object touches the selected object<br>Clicked - Updates the score when you click the selected object<br>Broadcast Listened - Updates the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be updated based on the trigger event happening</td></tr><tr><td>Operator </td><td>Define the operator to multiply by. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td>Update By</td><td>Define an integer (positive or negative) to change the score by. For instance, if the operator is Add and Update By is given the value 10, then the score is increased by 10 every time the trigger event defined in Update When happens</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [UpdateScoreTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#updatescoretemplate)

### Reset Score

You can reset  a player's score in Terra Creator Studio:

To reset the player score using logic templates, you need to add the Reset Score logic template using these steps:

1. Go to the Logic Tab.
2. Select Reset Score under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for resetting the score. There are four triggers allowed:<br>Player Touches- Resets the score when the player touches the selected object<br>Other Object Touches - Resets the score when another object touches the selected object<br>Clicked - Resets the score when you click the selected object<br>Broadcast Listened - Resets the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be reset based on the trigger event happening</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

You can choose not to use any logic template and directly use the T# wrapper for resetting score - the  [ResetScoreTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#resetscoretemplate)

### Increase Player HP

When triggered, the Increase HP (HP stands for Health Points) logic template  boosts the player's health. The behavior can be activated in response to various events, such as the player collecting coins or other items that improve health.&#x20;

To add the Increase HP logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Increase Player HP under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour<br>- After a broadcast message has been received by the object<br>- When the player touches the object</td></tr><tr><td>By Point</td><td>The player's health will increase by the defined amount when the behaviour is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health increases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health increases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent everytime the player health increases.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.&#x20;

### Decrease Player HP

In games, lowering the player's health as a result of certain interactions is a common mechanic. The Decrease Player HP Logic template reduces the player's health when specific triggers are activated.

To add the Decrease Player HP logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Decrease Player HP under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="291">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.</td></tr><tr><td>By Point</td><td>The player's health will decrease by the defined amount when the behaviour is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health decreases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health decreases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent everytime the player health decreases.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.&#x20;

### Reset Player Health

When a player interacts with an object tagged with the Reset Player Health logic template, the player's health is fully restored. This can be useful when a player respawns after dying, enters a safe zone, collects healing items, or faces similar situations.

To add the Reset Player Health logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Reset Player Health under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When the object is clicked.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health is reset</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health is reset</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when health is restored.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.&#x20;

### Update Magnet

The Update Magnet behavior increases the player's magnetic range, allowing them to collect items from a larger radius compared to the initial specified range.

To add the Update Magnet logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Update Magnet under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

| Parameter          | Description                                                                                                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Change Magnet When | <p>Define the action that will trigger a change in the magnetic field. The actions could be:<br>- After a broadcast message received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></p> |
| Radius             | The amount defined will act as the updated radius                                                                                                                                                                                                                                        |
| Play SFX           | Choose a sound effect to play when the magnet range is updated                                                                                                                                                                                                                           |
| Play VFX           | Choose a visual effect to play when the magnet range is updated                                                                                                                                                                                                                          |
| Broadcast Data     | <p>Define a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the magnetic range is updated</p>                                                                                                                                             |

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [ChangeMagnetTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#changemagnettemplate)

### Change Player Speed

Applying the Change Player Speed template changes the speed of the player to the desired value.&#x20;

To add the Change Player Speed logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Change Player Speed under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Change On When</td><td><p></p><p>Define the trigger for changing the speed. The four available triggers are:</p><ul><li><strong>Player Touches</strong></li><li><strong>Other Object Touches</strong></li><li><strong>Clicked</strong></li><li><strong>Broadcast Listened</strong></li></ul></td></tr><tr><td>Modifier</td><td>Define the modifier: <br>1. Set - Set to a defined value <br>2. Multiply - Multiply by the given value<br>3. Add - Increase by the given value<br>4. Subtract - Subtract the given value<br>5. Divide - Divide by the given value</td></tr><tr><td>Speed </td><td>Specify the value to apply the modifier to the current speed</td></tr><tr><td>SFX / VFX</td><td>Specify the SFX and VFX to be played upon execution</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [ChangePlayerSpeedTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#changeplayerspeedtemplate)

### Level Up

Level up behaviour is used to upgrade different in-game assets based on the the upgrade paths of objects defined using the [Level Mapper](../conceptual-guides/adding-global-logic-components.md) game system.

To add the Level Mapper logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Level Mapper under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Level up when</td><td>You can choose the trigger to activate the behaviour <br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play on execution</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play on execution</td></tr><tr><td>Manager group</td><td>Helps to choose the score group based on which the Level up will be decided</td></tr><tr><td>Broadcast Success</td><td>Define a broadcast to be generated when the level up is successful</td></tr><tr><td>Broadcast Fails </td><td>Define the broadcast to be generated when the level up fails</td></tr><tr><td>Execute Times</td><td>Number of times behaviour need to be excuted </td></tr></tbody></table>

There are currently no available T# Wrappers for this template.&#x20;

### Stop Player Template

When a player comes into contact with an asset that has the StopPlayerMovement logic template applied, the player's motion in the game environment is halted. This logic template locks the player in their current position and deactivates any movement through the controller.

To add the Stop Player Movement logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Stop Player Movement under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="246">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the player stops moving.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the player stops moving.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player stops moving again.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.&#x20;

### Change Player Speed

Applying the Change Player Speed template changes the speed of the player to the desired value.&#x20;

To add the Change Player Speed logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Change Player Speed under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Change On When</td><td><p></p><p>Define the trigger for changing the speed. The four available triggers are:</p><ul><li><strong>Player Touches</strong></li><li><strong>Other Object Touches</strong></li><li><strong>Clicked</strong></li><li><strong>Broadcast Listened</strong></li></ul></td></tr><tr><td>Modifier</td><td>Define the modifier: <br>1. Set - Set to a defined value <br>2. Multiply - Multiply by the given value<br>3. Add - Increase by the given value<br>4. Subtract - Subtract the given value<br>5. Divide - Divide by the given value</td></tr><tr><td>Speed </td><td>Specify the value to apply the modifier to the current speed</td></tr><tr><td>SFX / VFX</td><td>Specify the SFX and VFX to be played upon execution</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [ChangePlayerSpeedTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#changeplayerspeedtemplate)
