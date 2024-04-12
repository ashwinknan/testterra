---
description: The basic building blocks of game logic in Terra Studio
---

# Configuring Behaviors

To make our game interactive, we introduce Behavior Blocks. After setting up the game area and character, Behavior Blocks bring the game to life. They change a simple, static game into an engaging world that reacts to what the player does.

## What is a Behavior?

A "Behavior" is a modular logic block that is added to an Asset.  It contains instructions on how  the Player, Assets and Game Systems should behave.  Here are some important things to remember about an asset&#x20;

1. A Behavior is always added to an Asset.
2. Execution of a Behavior is always triggered by a Behavior Start Event
3. A Behavior can affect not only the Asset to which it is attached, but also other Assets, Game Scene Objects and Game Systems&#x20;

## Start Events for Behavior blocks&#x20;

Behavior blocks in Terra Studio start executing only when one of five events occur - Mouse Click, Broadcast Listened, Player Touch, Other Object Touch and Game Start.&#x20;

### Game Start

When you set the Start Event to Game Start, the behavior begins as soon as the game starts.&#x20;

### Mouse Click

When you click your mouse, the Behavior begins.

### Player Touch

When the Start Event is set to either Player Touch or Player Collide, the Behavior activates immediately after the Player touches or collides with the Asset’s collider.

### Other Object Touch

When the Start Event is "Other Object Touch," the Behavior starts when the other object's collision boundary touches the collision boundary of the object with the Behavior.

### Broadcast Listened

When you choose "Broadcast Listened" as the Start event, the Behavior only starts if it gets a specific signal. You must name the trigger signal. For example, if you set "Broadcast Listened" to react to `portal_opened`, then the Behavior will only start when the `portal_opened` signal occurs in the game.

## Effects of Behavior Blocks

A Behavior block when added to an Asset can be set up to not only affect that Asset, but also other Assets, the Player, the Game Scene or even Game Systems.&#x20;

The most common effects of Behavior blocks are :&#x20;

* Change in Player or Asset properties&#x20;
* Change in Game Scene Environment
* Change in Game Systems&#x20;
* Change in an Asset's Orientation&#x20;
* Create or Eliminates existing Game Scene Objects.
* Generate a Broadcast Signal
* Enable an SFX or Particle

The last two effects - generating a broadcast signal and enabling an SFX or VFX is present in every behavior.&#x20;

The other effects can be configured in the Editable Properties of each behavior.&#x20;

## Adding Behavior Blocks

To add behavior to an asset and customise it, follow these steps:

1. Select the Asset in the scene editor or through the Layers Panel.
2. Click Add Behaviour in the Inspector Panel.
3. You'll see selector with a search bar listing all possible behaviors. Choose the behavior you want and click "OK".
4. The Behavior has been added to the Asset. Scroll down in the Inspector panel to customize it. You can change its settings using the fields provided.
5. Once you make changes, click the Save button in the main toolbar.&#x20;

## Parallel Execution of Behavior Blocks

You can execute multiple Behaviors on the same Asset in parallel. Each behavior can function independently and gets triggered by its own Start Event. &#x20;

## Sequential Execution of Behaviors&#x20;

You can execute behaviors sequentially one after the other  with broadcast signals. You need to do the following:

1. **First Behavior - Sending Signal**
   * Set the action of the first behavior to **Broadcast Custom signal**.
   * For the signal value, input any alphanumeric signal name. This will be sent out once the behavior completes its task.
2. **Second Behavior - Waiting for Signal**
   * Change the Start Event of the second behavior to **Broadcast Listened**.
   * Specify the alphanumetic signal you set in the first step as the signal to listen for. This ensures the behavior only starts after receiving signal from the first behavior.

## Behavior Categories

To streamline development, behaviors are grouped into three distinct categories:

* **Dependent Behaviors:** Function based on other behaviors or specific events.
* **Independent Behaviors:** Operate without any external dependencies.
* **Joiners:** Serve as a bridge, connecting various behaviors together.

## List of Available Behavior Blocks

Terra Studio has a wide selection of Behavior blocks for you to choose from. A Behavior can be added to any Asset and configured to elicit the interactivity you want in the game. The table below shows a list of Behavior blocks and a short description of what they do. A detailed description of each behavior is given in the respective behavior page.&#x20;

### Basic Behavior Blocks

<table><thead><tr><th width="263">Behavior Block</th><th>Description</th></tr></thead><tbody><tr><td><a href="click.md">Click</a></td><td>Can generate a broadcast signal or enable SFX / VFX on a mouse-click by the user</td></tr><tr><td><a href="collide.md">Collide</a></td><td>Can generate a broadcast signal or enable SFX / VFX on collision by another Asset or the Player</td></tr></tbody></table>

### Behavior blocks that affect Asset position, size and movement

<table><thead><tr><th width="261">Behavior Block</th><th>Description</th></tr></thead><tbody><tr><td><a href="move.md">Move</a></td><td>Moves the Asset in a straight line path to a specified new position from its starting point.</td></tr><tr><td><a href="interpolate-points.md">Interpolate Points </a></td><td>Shifts the Asset from its starting spot through a path of straight or curved points as needed.</td></tr><tr><td><a href="move-to-player.md">Move To Player</a></td><td>Moves the Asset to the Player</td></tr><tr><td>Advance Move</td><td>An enhanced Move block that moves an Asset but includes more sophisticated options for customisation</td></tr><tr><td><a href="stop-move.md">Stop Move</a></td><td>Disables the Move block on the Asset</td></tr><tr><td><a href="rotate.md">Rotate</a></td><td>Rotates the Asset about a chosen axis</td></tr><tr><td>Advance Rotate</td><td>An enhanced Rotate block that allows you to rotate an Asset about a chosen axis, offering additional sophisticated options.</td></tr><tr><td>Rotate (Oscillate)</td><td>Oscilates the Asset about a specified axis within a specified rotation about the initial position</td></tr><tr><td><a href="stop-rotate.md">Stop Rotate</a></td><td>Disables the Rotate block on the Asset</td></tr><tr><td>Grow / Shrink</td><td>Increases or decreases the size of the Asset</td></tr></tbody></table>

### Behavior blocks that affect Player position and movement

<table><thead><tr><th width="261">Behavior block</th><th>Description</th></tr></thead><tbody><tr><td>Teleport Player</td><td>Instantly spawns the Player in a new specified position</td></tr><tr><td><a href="jump-pad.md">Jump Pad</a></td><td>Creates a jump enhancement for the player upon contact</td></tr><tr><td><a href="stop-player-movement.md">Stop Player Movement</a></td><td>Stops any movement of the player</td></tr><tr><td><a href="update-magnet.md">Update Magnet</a></td><td> increases the player's magnetic range</td></tr></tbody></table>



### Behavior blocks that affect Game Systems

<table><thead><tr><th width="259">Behavior block</th><th>Description</th></tr></thead><tbody><tr><td><a href="update-score.md">Update Score</a></td><td>Updates a specific score group to a new specified value</td></tr><tr><td><a href="reset-score.md">Reset Score</a></td><td>Resets the specified score group to zero</td></tr><tr><td><a href="update-timer.md">Update Timer</a></td><td>Updates the timer  to a new specified value</td></tr><tr><td><a href="reset-timer.md">Reset Timer</a></td><td>Resets the timer to zero</td></tr><tr><td><a href="increase-player-health.md">Increase Player Health</a></td><td>Increases the player Health value by the specific amount</td></tr><tr><td><a href="decrease-player-health.md">Decrease Player Health</a></td><td>Decreases the player Health value by a specific amount</td></tr><tr><td><a href="reset-player-health.md">Reset Player Health</a></td><td>Resets the player Health value to zero</td></tr><tr><td>Level Up</td><td>Guides the Level Mapper on how to increase a property's level to the next tier.</td></tr><tr><td><a href="https://app.gitbook.com/o/qrOp5exMLmnPZxfhxQgu/s/Gd8RR9TPbiGza2LHqkh7/~/changes/85/overview/building-blocks-of-a-terra-game/configuring-behaviors/load-scene">Load Scene</a></td><td>Loads a New Scene</td></tr><tr><td><a href="showui/">ShowUI</a></td><td>Displays a UI on the screen</td></tr></tbody></table>

### Behavior blocks that affect the relationship of an Asset with the player

<table><thead><tr><th width="261">Behavior block</th><th>Description</th></tr></thead><tbody><tr><td>Carriable</td><td>Enables an Asset to be carried by the Player. The Asset will now move with the Player</td></tr><tr><td>Deposit</td><td>Enables the Player to transfer the Carriable Asset and deposit it to a new Asset which is a storage</td></tr><tr><td><a href="collectable.md">Collectable</a></td><td>Enables an object to be collected by the player and update the game score. Used in Power-ups. </td></tr></tbody></table>

### Behavior blocks that create or destroy the Player or Assets

<table><thead><tr><th width="262">Behavior block</th><th>Description</th></tr></thead><tbody><tr><td><a href="destroy-self.md">Destroy Self</a></td><td><p>Destroys the Asset from the sc</p><p>ene</p></td></tr><tr><td><a href="kill-player.md">Kill Player</a></td><td>Respawns the player to the start of the level</td></tr><tr><td><a href="instantiate.md">Instantiate</a></td><td>Spawns new instances of an Asset at a specified rate (per x seconds)</td></tr><tr><td>Instantiate On Event</td><td>Spawns new instances of an Asset when a Start Event happens </td></tr><tr><td><a href="debris.md">Debris</a> </td><td>defines the post-destruction landscape</td></tr><tr><td><a href="debris-destructible.md">Debris Destructible</a></td><td> annihilate objects within the game environment</td></tr></tbody></table>

### Miscellaneous Behavior blocks

### Behavior blocks that act as joiners

<table><thead><tr><th width="264">Behavior Block</th><th></th></tr></thead><tbody><tr><td><a href="delay.md">Delay</a></td><td>Introduces a delay of a specified time</td></tr><tr><td><a href="and-operator.md">And Operator</a></td><td>Acts as a gate that sends out a broadcast signal only after all required conditions are met. These conditions are broadcast signals from various sources. It won't activate until every condition is satisfied.</td></tr><tr><td><a href="or-operator.md">Or Operator</a></td><td>Acts as a gate that sends out a broadcast signal only after any one of the  required conditions are met. These conditions are broadcast signals from various sources. </td></tr></tbody></table>

