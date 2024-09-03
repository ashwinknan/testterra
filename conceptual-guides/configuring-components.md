# Configuring Components

To make our game interactive, we introduce Components, which brings the game to life and changes a simple, static game into an engaging world that reacts to what the player does.

There are two ways to use Components in Terra Studio&#x20;

1. [Using pre-built Logic Components](configuring-components.md#using-pre-built-logic-components)
2. [Scripting custom logic components](configuring-components.md#scripting-your-own-component-in-t)

## Using pre-built Logic Components

To accelerate the time to create games, Terra Creator Studio also provides pre-built Logic Template components. These Templates represent various logical operations, conditions, and actions, and can be easily selected from the Editor and dragged and dropped onto Assets.

### What is a pre-built logic component?

A pre-built logic component is always added to an Asset GameObject.  It contains pre-built instructions on how  the Player and the other GameObjects in the game should behave.  Here are some important things to remember about templates

1. A Logic Template Component is always added to an Asset GameObject.
2. Execution of a Logic Template Component is always triggered by a Start Event
3. A Logic Template Component can affect not only the Asset GameObject to which it is attached, but also other GameObjects&#x20;

#### Start Events for Logic Templates

Logic Templates in Terra Studio start executing any of the five events listed below occur:

<table><thead><tr><th width="215">Start Event Name</th><th>Logic Template Component is executed when</th></tr></thead><tbody><tr><td>Game Start</td><td>The game starts</td></tr><tr><td>Mouse Click</td><td>You click the mouse</td></tr><tr><td>Player Touch / Player Collide</td><td>The Player touches or collides with the Asset’s collider.</td></tr><tr><td>Other Object Touch</td><td>The other Asset's collider touches the collider of the asset to which the Logic Template is attached</td></tr><tr><td>Broadcast Listened</td><td>A specified game signal is generated in the game. <br><em>E.g - If the Start Event is set to Broadcast Listened - 'level_finish', the logic template will execute only when the game signal 'level_finish' is generated during the game.</em></td></tr></tbody></table>

### Effects of Logic Template Components

A logic template Component when added to an Asset can be set up to not only affect that Asset GameObject, but also other GameObjects.&#x20;

The most common effects of logic templates are :&#x20;

* Change in Player or GameObject properties&#x20;
* Change in Game Systems&#x20;
* Change in a GameObject's Orientation&#x20;
* Create or Eliminates existing GameObjects.
* Generate Custom Broadcasts
* Enabling an SFX or VFX GameObject

The last two effects - Generating Custom Broadcasts and enabling an SFX GameObject or a VFX GameObject is present in every logic template&#x20;

The other effects can be configured in the Editable Properties of each logic template&#x20;

### How to add pre-built Logic Components

To add a logic template to an asset and customise it, follow these steps:

1. Select the Asset GameObject in the scene editor or through the Layers Panel.
2. Click the Logic tab in the Quick Access Menu on the left
3. You'll see a Logic Selector with all the possible logic templates&#x20;
4. Choose the logic template you want and drag and drop into the Asset
5. The logic template has been added to the Asset.&#x20;
6. You can configure the logic template's properties by selecting the Advanced Mode toggle button and editing the various accessible fields.
7. Once you make changes, click the Save button in the main toolbar.&#x20;

### How to execute pre-built logic templates in parallel

You can execute multiple logic templates on the same Asset in parallel. Each logic template can function independently and gets triggered by its own Start Event. &#x20;

### How to sequentially execute logic templates

&#x20;You can execute logic templates sequentially one after the other by using the Custom Broadcast Start Event.&#x20;

The first logic template can generate a custom broadcast signal upon execution. This broadcast signal can then be the start event of the second logic template

### List of Available Logic Template Components

Terra Studio has a wide selection of logic template components for you to choose from. A logic template  componnent can be added to any Asset GameObject and configured to elicit the interactivity you want in the game. The table below shows a list of logic template and a short description of what they do. A detailed description of each logic template is given in the respective logic template page.&#x20;

#### Scene Management

<table><thead><tr><th width="259">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#checkpoint">Checkpoint</a></td><td>Restarts the game from a specific point if you fail a challenge or lose a life</td></tr><tr><td><a href="configuring-components.md#update-timer">Update Timer</a></td><td>Updates the timer  to a new specified value</td></tr><tr><td><a href="configuring-components.md#reset-timer">Reset Timer</a></td><td>Resets the timer to zero</td></tr><tr><td><a href="configuring-components.md#load-scene">Load Scene</a></td><td>Loads a New Scene</td></tr><tr><td><a href="configuring-components.md#random-level-selector">Random Level Selector</a></td><td>Loads a random new scene on game start instead of the default scene</td></tr></tbody></table>

#### Mechanics

<table><thead><tr><th width="255">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#collectable">Collectable</a></td><td>Enables an object to be collected by the player and update the game score. Used in Power-ups. </td></tr><tr><td><a href="configuring-components.md#teleport-player">Teleport Player</a></td><td>Instantly spawns the Player in a new specified position</td></tr><tr><td><a href="configuring-components.md#jump-pad">Jump Pad</a></td><td>Creates a jump enhancement for the player upon contact</td></tr><tr><td><a href="configuring-components.md#carryable">Carryable</a></td><td>Enables an Asset to be carried by the Player. The Asset will now move with the Player</td></tr><tr><td><a href="configuring-components.md#deposit">Deposit</a></td><td>Enables the Player to transfer the Carriable Asset and deposit it to a new Asset which is a storage</td></tr><tr><td><a href="configuring-components.md#modify-carryable">Modify Carryable</a></td><td>Modifies the number of carryables you have</td></tr><tr><td><a href="configuring-components.md#kill-player">Kill Player</a></td><td>Respawns the player to the start of the level</td></tr><tr><td><a href="configuring-components.md#hinge-joint">Hinge Joint</a></td><td>Enables assets to rotate about a defined hinge like a dore</td></tr><tr><td><a href="configuring-components.md#explosive-force">Explosive Force</a></td><td>Applies a force / impulse on a radius</td></tr><tr><td><a href="configuring-components.md#add-force">Add Force</a></td><td>Applies a force on an object and allows it to follow physics </td></tr><tr><td><a href="configuring-components.md#treadmill">Treadmill</a></td><td>Enables treadmill-like motion on contact</td></tr><tr><td><a href="configuring-components.md#multi-point-move">Multipoint Move</a></td><td>Shifts the Asset from its starting spot through a path of straight or curved points as needed.</td></tr><tr><td><a href="configuring-components.md#attach-object">Attach Object</a></td><td>Parents an object to another object</td></tr></tbody></table>

#### Actions

<table><thead><tr><th width="260">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#destroy">Destroy</a></td><td>Destroys the Asset from the scene</td></tr><tr><td><a href="configuring-components.md#set-position">Set Position</a></td><td>Changes the Asset's position</td></tr><tr><td><a href="configuring-components.md#advance-instantiate">Advance Instantiate</a></td><td>Spawns an instance of the player (with advanced settings)</td></tr><tr><td><a href="configuring-components.md#grow-shrink">Grow / Shrink</a></td><td>Increases or decreases the size of the Asset</td></tr><tr><td><a href="configuring-components.md#move">Move</a></td><td>Moves the Asset in a straight line path to a specified new position from its starting point.</td></tr><tr><td><a href="configuring-components.md#rotate">Rotate</a></td><td>Rotates the Asset about a chosen axis</td></tr><tr><td><a href="configuring-components.md#movetoplayer">MoveTo Player</a></td><td>Moves the Asset to the Player</td></tr><tr><td><a href="configuring-components.md#rotate-oscillate">Rotate Oscillate</a></td><td>Oscilates the Asset about a specified axis within a specified rotation about the initial position</td></tr><tr><td><a href="configuring-components.md#basic-instantiate">Basic Instantiate</a></td><td>Spawns an instance of the player</td></tr><tr><td><a href="configuring-components.md#bump">Bump</a></td><td>Bounce back when you run into it</td></tr></tbody></table>

#### Conditionals

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#switch">Switch</a></td><td>Helps activate or deactivate behaviors depending on the triggers associated with each action. </td></tr><tr><td><a href="configuring-components.md#or-gate">OR Gate</a></td><td>Acts as a gate that sends out a broadcast signal only after any one of the  required conditions are met. These conditions are broadcast signals from various sources. </td></tr><tr><td><a href="configuring-components.md#and-gate">AND Gate</a></td><td>Acts as a gate that sends out a broadcast signal only after all required conditions are met. These conditions are broadcast signals from various sources. It won't activate until every condition is satisfied.</td></tr><tr><td><a href="configuring-components.md#tick">Tick</a></td><td>Generates a broadcast at a pre-defined time or time-intervals</td></tr></tbody></table>

#### Triggers

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#collide">Collide</a></td><td>Uses contact of collider of the player as a trigger and allows you to generate a broadcast</td></tr><tr><td><a href="configuring-components.md#click">Click</a></td><td>Uses mouse click as a trigger and allows you to generate broadcast</td></tr><tr><td><a href="configuring-components.md#delay">Delay</a></td><td>Introduces a delay of a specified time</td></tr></tbody></table>

#### Effects

<table><thead><tr><th width="263">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#stop-rotate">Stop Rotate</a></td><td>Stops Rotation </td></tr><tr><td><a href="configuring-components.md#showui">ShowUI</a></td><td>Displays a UI on the screen</td></tr><tr><td><a href="configuring-components.md#stop-animation">Stop Animation</a></td><td>Stops Animation </td></tr><tr><td><a href="configuring-components.md#play-players-animation">Play Player's Animation</a></td><td>Plays animation of the player</td></tr></tbody></table>

#### PlayerStats

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="configuring-components.md#update-score">Update Score</a></td><td>Updates a specific score group to a new specified value</td></tr><tr><td><a href="configuring-components.md#reset-score">Reset Score</a></td><td>Resets the specified score group to zero</td></tr><tr><td><a href="configuring-components.md#increase-player-hp">Increase Player HP</a></td><td>Increases the player Health value by the specific amount</td></tr><tr><td><a href="configuring-components.md#decrease-player-hp">Decrease Player HP</a></td><td>Decreases the player Health value by a specific amount</td></tr><tr><td><a href="configuring-components.md#reset-player-health">Reset Player Health</a></td><td>Resets the player Health value to zero</td></tr><tr><td><a href="configuring-components.md#level-up">Level Up</a></td><td>Guides the Level Mapper on how to increase a property's level to the next tier.</td></tr><tr><td><a href="configuring-components.md#update-magnet">Update Magnet</a></td><td>Changes the magnet range for the player's collection</td></tr><tr><td><a href="configuring-components.md#stop-player-template">Stop Player Movement</a></td><td>Stops or starts the player movements</td></tr><tr><td><a href="configuring-components.md#change-player-speed">Change Player Speed</a></td><td>Changes the speed of movement of the player</td></tr></tbody></table>



## Scripting your own component in T\#

**Terra Creator Studio** enables experienced game developers to implement custom logic using a scripting language called **T# (T-Sharp)**. T# is very similar to Unity's C#, making it easy for Unity developers to learn. The links below provide detailed guidance on writing T-Sharp code:

[Basics of Scripting in T#](../scripting-custom-logic-components/creating-and-using-t-scripts.md)

[Unsupported Functionalities in T#](../scripting-custom-logic-components/unsupported-functionalities-in-t.md)&#x20;

## Hybrid Approach - Logic Template Component + Custom Script Components

Logic Components are useful for both beginners and experienced developers. For beginners,  they reduce the need for extensive coding knowledge. For senior developers, they eliminate the need to write code from scratch for simple game interactions and save time and effort.

The limitation of Logic Template Components is the inflexibility in customizing interactions, as only exposed properties are editable from the editor. We address this by providing wrappers for Logic Templates, customizable via T-Sharp code. These wrappers expose all editable properties to the developer, allowing for more complex interactions than the editor interface permits.

You can read more about how to access the Logic Templates through T-Sharp code in the documentation for [Logic Template Wrappers](../scripting-custom-logic-components/t-logic-component-template-wrappers.md).&#x20;

