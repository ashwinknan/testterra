# Configuring Game Logic

To make our game interactive, we introduce game logic, which brings the game to life and changes a simple, static game into an engaging world that reacts to what the player does.

There are three ways to add game logic in Terra Studio&#x20;

1. [Writing your own code in T-Sharp](configuring-game-logic.md#writing-your-own-code-in-t)
2. [Using Logic Templates](configuring-game-logic.md#using-logic-templates)
3. [Hybrid Approach - Logic Templates + Coding](configuring-game-logic.md#hybrid-approach-templates--coding)

## Writing your own code in T\#

**Terra Creator Studio** enables experienced game developers to implement custom logic using a scripting language called **T# (T-Sharp)**. T# is very similar to Unity's C#, making it easy for Unity developers to learn. The links below provide detailed guidance on writing T-Sharp code:

[Basics of T-Sharp](../coding-using-t/t-basics.md)

[Differences between T# and C#](../coding-using-t/t-donts.md)

## Using Logic Templates

To accelerate the time to create games, Terra Creator Studio also provides pre-built logic blocks or components, known as Templates. These Templates represent various logical operations, conditions, and actions, and can be easily selected from the Editor and dragged and dropped onto Assets.

### What is a Logic Template?

A "Logic Template" is always added to an Asset.  It contains pre-built instructions on how  the Player, Assets and Game Systems should behave.  Here are some important things to remember about templates

1. A Logic Template is always added to an Asset.
2. Execution of a Logic Template is always triggered by a Start Event
3. A Logic Template can affect not only the Asset to which it is attached, but also other Assets, Game Scene Objects and Game Systems&#x20;

### Start Events for Logic Templates

Logic Templates in Terra Studio start executing any of the five events listed below occur:

<table><thead><tr><th width="215">Start Event Name</th><th>Logic Template is executed when</th></tr></thead><tbody><tr><td>Game Start</td><td>The game starts</td></tr><tr><td>Mouse Click</td><td>You click the mouse</td></tr><tr><td>Player Touch / Player Collide</td><td>The Player touches or collides with the Asset’s collider.</td></tr><tr><td>Other Object Touch</td><td>The other Asset's collider touches the collider of the asset to which the Logic Template is attached</td></tr><tr><td>Broadcast Listened</td><td>A specified game signal is generated in the game. <br><em>E.g - If the Start Event is set to Broadcast Listened - 'level_finish', the logic template will execute only when the game signal 'level_finish' is generated during the game.</em></td></tr></tbody></table>

### Effects of Logic Templates

A logic template when added to an Asset can be set up to not only affect that Asset, but also other Assets, the Player, the Game Scene or even Game Systems.&#x20;

The most common effects of logic templates are :&#x20;

* Change in Player or Asset properties&#x20;
* Change in Game Scene Environment
* Change in Game Systems&#x20;
* Change in an Asset's Orientation&#x20;
* Create or Eliminates existing Game Scene Objects.
* Generate a Custom Broadcast Signal
* Enable an SFX or Particle

The last two effects - generating a broadcast signal and enabling an SFX or VFX is present in every logic template&#x20;

The other effects can be configured in the Editable Properties of each logic template&#x20;

### How to add Logic Templates

To add a logic template to an asset and customise it, follow these steps:

1. Select the Asset in the scene editor or through the Layers Panel.
2. Click the Logic tab in the Quick Access Menu on the left
3. You'll see a Logic Selector with all the possible logic templates&#x20;
4. Choose the logic template you want and drag and drop into the Asset
5. The logic template has been added to the Asset.&#x20;
6. You can configure the logic template's properties by selecting the Advanced Mode toggle button and editing the various accessible fields.
7. Once you make changes, click the Save button in the main toolbar.&#x20;

### How to execute logic templates in parallel

You can execute multiple logic templates on the same Asset in parallel. Each logic template can function independently and gets triggered by its own Start Event. &#x20;

### How to sequentially execute logic templates

&#x20;You can execute logic templates sequentially one after the other by using the Custom Broadcast Start Event.&#x20;

The first logic template can generate a custom broadcast signal upon execution. This broadcast signal can then be the start event of the second logic template

### List of Available Logic Templates

Terra Studio has a wide selection of logic templates for you to choose from. A logic template can be added to any Asset and configured to elicit the interactivity you want in the game. The table below shows a list of logic template and a short description of what they do. A detailed description of each logic template is given in the respective logic template page.&#x20;

#### Basic Logic Templates

<table><thead><tr><th width="263">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="../logic-templates/click.md">Click</a></td><td>Can generate a broadcast signal or enable SFX / VFX on a mouse-click by the user</td></tr><tr><td><a href="../logic-templates/collide.md">Collide</a></td><td>Can generate a broadcast signal or enable SFX / VFX on collision by another Asset or the Player</td></tr></tbody></table>

#### Logic Templates that affect Asset position, size and movement

<table><thead><tr><th width="261">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="../logic-templates/move.md">Move</a></td><td>Moves the Asset in a straight line path to a specified new position from its starting point.</td></tr><tr><td><a href="../logic-templates/interpolate-points.md">Interpolate Points </a></td><td>Shifts the Asset from its starting spot through a path of straight or curved points as needed.</td></tr><tr><td><a href="../logic-templates/move-to-player.md">Move To Player</a></td><td>Moves the Asset to the Player</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/advance-move">Advance Move</a></td><td>An enhanced Move block that moves an Asset but includes more sophisticated options for customisation</td></tr><tr><td><a href="../logic-templates/stop-move.md">Stop Move</a></td><td>Disables the Move block on the Asset</td></tr><tr><td><a href="../logic-templates/rotate.md">Rotate</a></td><td>Rotates the Asset about a chosen axis</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/copy-of-rotate">Advance Rotate</a></td><td>An enhanced Rotate block that allows you to rotate an Asset about a chosen axis, offering additional sophisticated options.</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/rotate-oscillate">Rotate (Oscillate)</a></td><td>Oscilates the Asset about a specified axis within a specified rotation about the initial position</td></tr><tr><td><a href="../logic-templates/stop-rotate.md">Stop Rotate</a></td><td>Disables the Rotate block on the Asset</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/copy-of-rotate-oscillate">Grow / Shrink</a></td><td>Increases or decreases the size of the Asset</td></tr></tbody></table>

#### Logic Templates that affect Player position and movement

<table><thead><tr><th width="261">Logic Templates</th><th>Description</th></tr></thead><tbody><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/teleport-player">Teleport Player</a></td><td>Instantly spawns the Player in a new specified position</td></tr><tr><td><a href="../logic-templates/jump-pad.md">Jump Pad</a></td><td>Creates a jump enhancement for the player upon contact</td></tr><tr><td><a href="../logic-templates/stop-player-movement.md">Stop Player Movement</a></td><td>Stops any movement of the player</td></tr><tr><td><a href="../logic-templates/update-magnet.md">Update Magnet</a></td><td> increases the player's magnetic range</td></tr></tbody></table>



#### Logic Templates that affect Game Systems

<table><thead><tr><th width="259">Logic Templates</th><th>Description</th></tr></thead><tbody><tr><td><a href="../logic-templates/update-score.md">Update Score</a></td><td>Updates a specific score group to a new specified value</td></tr><tr><td><a href="../logic-templates/reset-score.md">Reset Score</a></td><td>Resets the specified score group to zero</td></tr><tr><td><a href="../logic-templates/update-timer.md">Update Timer</a></td><td>Updates the timer  to a new specified value</td></tr><tr><td><a href="../logic-templates/reset-timer.md">Reset Timer</a></td><td>Resets the timer to zero</td></tr><tr><td><a href="../logic-templates/increase-player-health.md">Increase Player Health</a></td><td>Increases the player Health value by the specific amount</td></tr><tr><td><a href="../logic-templates/decrease-player-health.md">Decrease Player Health</a></td><td>Decreases the player Health value by a specific amount</td></tr><tr><td><a href="../logic-templates/reset-player-health.md">Reset Player Health</a></td><td>Resets the player Health value to zero</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/">Level Up</a></td><td>Guides the Level Mapper on how to increase a property's level to the next tier.</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/85/overview/building-blocks-of-a-terra-game/configuring-behaviors/load-scene">Load Scene</a></td><td>Loads a New Scene</td></tr><tr><td><a href="../logic-templates/showui/">ShowUI</a></td><td>Displays a UI on the screen</td></tr></tbody></table>

#### Logic Templates that affect the relationship of an Asset with the player

<table><thead><tr><th width="261">Logic Templates</th><th>Description</th></tr></thead><tbody><tr><td>Carriable</td><td>Enables an Asset to be carried by the Player. The Asset will now move with the Player</td></tr><tr><td>Deposit</td><td>Enables the Player to transfer the Carriable Asset and deposit it to a new Asset which is a storage</td></tr><tr><td><a href="../logic-templates/collectable.md">Collectable</a></td><td>Enables an object to be collected by the player and update the game score. Used in Power-ups. </td></tr></tbody></table>

#### Logic Templates that create or destroy the Player or Assets

<table><thead><tr><th width="262">Logic Templates</th><th>Description</th></tr></thead><tbody><tr><td><a href="../logic-templates/destroy-self.md">Destroy Self</a></td><td>Destroys the Asset from the scene</td></tr><tr><td><a href="../logic-templates/kill-player.md">Kill Player</a></td><td>Respawns the player to the start of the level</td></tr><tr><td><a href="../logic-templates/instantiate-on-event.md">Instantiate</a></td><td>Spawns new instances of an Asset at a specified rate (per x seconds)</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/87/overview/building-blocks-of-a-terra-game/configuring-behaviors/copy-of-teleport-player">Instantiate On Event</a></td><td>Spawns new instances of an Asset when a Start Event happens </td></tr><tr><td><a href="../logic-templates/debris.md">Debris</a> </td><td>defines the post-destruction landscape</td></tr><tr><td><a href="../logic-templates/debris-destructible.md">Debris Destructible</a></td><td> annihilate objects within the game environment</td></tr></tbody></table>

#### Logic Templates that act as joiners

<table><thead><tr><th width="264">Logic Templates</th><th>Description</th></tr></thead><tbody><tr><td><a href="../logic-templates/delay.md">Delay</a></td><td>Introduces a delay of a specified time</td></tr><tr><td><a href="../logic-templates/and-operator.md">And Operator</a></td><td>Acts as a gate that sends out a broadcast signal only after all required conditions are met. These conditions are broadcast signals from various sources. It won't activate until every condition is satisfied.</td></tr><tr><td><a href="../logic-templates/or-operator.md">Or Operator</a></td><td>Acts as a gate that sends out a broadcast signal only after any one of the  required conditions are met. These conditions are broadcast signals from various sources. </td></tr></tbody></table>

## Hybrid Approach - Templates + Coding

Logic Templates are useful for both beginners and experienced developers. For beginners,  they reduce the need for extensive coding knowledge. For senior developers, they eliminate the need to write code from scratch for simple game interactions and save time and effort.

The limitation of Logic Templates is the inflexibility in customizing interactions, as only exposed properties are editable from the editor. We address this by providing wrappers for Logic Templates, customizable via T-Sharp code. These wrappers expose all editable properties to the developer, allowing for more complex interactions than the editor interface permits.

You can read more about how to access the Logic Templates through T-Sharp code in the documentation for [Logic Template Wrappers](../coding-using-t/t-logic-template-wrappers.md).&#x20;

