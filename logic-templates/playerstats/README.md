# PlayerStats

## Overview

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="update-score.md">Update Score</a></td><td>Updates a specific score group to a new specified value</td></tr><tr><td><a href="reset-score.md">Reset Score</a></td><td>Resets the specified score group to zero</td></tr><tr><td><a href="increase-player-hp.md">Increase HP</a></td><td>Increases the player Health value by the specific amount</td></tr><tr><td><a href="decrease-player-hp.md">Damage HP</a></td><td>Decreases the player Health value by a specific amount</td></tr><tr><td><a href="reset-player-health.md">Reset Health</a></td><td>Resets the player Health value to zero</td></tr><tr><td><a href="level-up.md">Level Up</a></td><td>Guides the Level Mapper on how to increase a property's level to the next tier.</td></tr><tr><td><a href="update-magnet.md">Change Magnet Range</a></td><td>Changes the magnet range for the player's collection</td></tr><tr><td><a href="stop-player-movement.md">Toggle Player Movement</a></td><td>Stops or starts the player movements</td></tr><tr><td>Change Player Speed</td><td>Changes the speed of movement of the player</td></tr></tbody></table>

## List of PlayerStats Logic Template Components

### Update Score

You may want to enhance the gameplay experience by adjusting the game [score ](../../conceptual-guides/setting-up-game-systems.md#score)when specific conditions are met. For instance:

* Update the score when the player collects items such as coins, gems, or power-ups. This promotes exploration and rewards the player's curiosity.
* Increase the score upon completing a level or reaching a milestone, such as finishing a race track or solving a puzzle.
* Award points for unique or challenging achievements outside the normal gameplay loop, such as discovering hidden areas.

You do this using the Update Score logic template component. To add the Update Score logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Update Score under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for updating the score. There are four triggers allowed:<br>Player Touches- Updates the score when the player touches the selected object<br>Other Object Touches - Updates the score when another object touches the selected object<br>Clicked - Updates the score when you click the selected object<br>Broadcast Listened - Updates the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be updated based on the trigger event happening</td></tr><tr><td>Operator </td><td>Define the operator to multiply by. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td>Update By</td><td>Define an integer (positive or negative) to change the score by. For instance, if the operator is Add and Update By is given the value 10, then the score is increased by 10 every time the trigger event defined in Update When happens</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [UpdateScoreTemplate](../../coding-using-t/t-logic-template-wrappers.md#updatescoretemplate)

### Reset Score

You can reset  a player's score in Terra Creator Studio:

To reset the player score using logic templates, you need to add the Reset Score logic template using these steps:

1. Go to the Logic Tab.
2. Select Reset Score under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for resetting the score. There are four triggers allowed:<br>Player Touches- Resets the score when the player touches the selected object<br>Other Object Touches - Resets the score when another object touches the selected object<br>Clicked - Resets the score when you click the selected object<br>Broadcast Listened - Resets the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be reset based on the trigger event happening</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

### Resetting the Player Score through T\#

You can choose not to use any logic template and directly use the T# wrapper for resetting score - the  [ResetScoreTemplate](../../coding-using-t/t-logic-template-wrappers.md#resetscoretemplate)
