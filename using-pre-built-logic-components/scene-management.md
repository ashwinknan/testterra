# Scene Management

## Overview

Scene Management Logic Template components are pre-built components aimed to help game developers readily build logic that affect the entire scene.&#x20;

<table><thead><tr><th width="259">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="scene-management.md#checkpoint">Checkpoint</a></td><td>Restarts the game from a specific point if you fail a challenge or lose a life</td></tr><tr><td><a href="scene-management.md#update-timer">Update Timer</a></td><td>Updates the timer  to a new specified value</td></tr><tr><td><a href="scene-management.md#reset-timer">Reset Timer</a></td><td>Resets the timer to zero</td></tr><tr><td><a href="scene-management.md#load-scene">Load Scene</a></td><td>Loads a New Scene</td></tr><tr><td><a href="scene-management.md#random-level-selector">Random Level Selector</a></td><td>Loads a random new scene on game start instead of the default scene</td></tr></tbody></table>

## All Overall Game Logic Template Components

### Checkpoint

A checkpoint is a designated spot where player progress is saved automatically or manually. These markers allow you to restart the game from that specific point if you fail a challenge, lose a life, or need to pause the game.

To add the checkpoint logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Checkpoint under the header "Game".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter                                        | Description                                                                                                                                               |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Play SFX`</mark>      | Choose a short chime to play when you arrive at checkpoint                                                                                                |
| <mark style="color:blue;">`Play VFX`</mark>      | Choose a visual effect to play when you arrive at the checkpoint                                                                                          |
| <mark style="color:blue;">`BroadcastData`</mark> | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the you arrive at the checkpoint.</p> |

You can further  customize the  Checkpoint logic template in T# by accessing its T# Wrapper - [CheckpointTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#checkpointtemplate).&#x20;

### Update Timer

In the game, significant events such as completing tasks or defeating enemies can adjust the timer, adding bonus time or starting time-limited challenges. Conversely, mistakes or failures can reduce the time. The Update Timer template is used to handle these changes.

To add the Update Timer logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Update Timer under the header "Game".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameters</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Update When</code></mark></td><td><p></p><p>Select a trigger from the dropdown to activate the logic template:</p><ul><li><strong>Player Touches</strong>: Resets the timer when the player touches the selected object.</li><li><strong>Other Object Touches</strong>: Resets the timer when another object touches the selected object.</li><li><strong>Clicked</strong>: Resets the timer when you click the selected object.</li><li><strong>Broadcast Listened</strong>: Resets the timer when it receives a broadcast</li></ul></td></tr><tr><td><mark style="color:blue;"><code>Operation</code></mark></td><td>Define the operator that will modify the timer. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td><mark style="color:blue;"><code>Update By</code></mark></td><td>The quantity specified in this context will determine the extent to which the timer is modified.</td></tr><tr><td><mark style="color:blue;"><code>Sound Effect on Start</code></mark></td><td>Choose a sound effect to play when the timer value is updated.</td></tr><tr><td><mark style="color:blue;"><code>Visual Effect on Start</code></mark></td><td>Choose a visual effect to play when the timer value is updated.</td></tr><tr><td><mark style="color:blue;"><code>Broadcast on Update</code></mark></td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the timer is updated.</td></tr><tr><td><mark style="color:blue;"><code>Execute always</code></mark></td><td>This toggle, when activated, will always execute this. When off, it will execute it only once.</td></tr></tbody></table>

You can further  customize the  Checkpoint logic template in T# by accessing its T# Wrapper - [UpdateTimerTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#updatetimertemplate). &#x20;

### Reset Timer

The Reset Timer behavior resets the game timer to its initial value without affecting the game experience. If it's a countdown timer, the time is reset to the starting value. If it's a count-up timer, the time is reset to 0 seconds.

You can customize the template parameters according to the game requirements:

To add the Reset Timer logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Reset Timer under the header "Game".
3. Drag and drop it onto the desired asset.



You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Reset When</code></mark></td><td><p>Select a trigger from the dropdown to activate the logic template:</p><ul><li><strong>Player Touches</strong>: Resets the timer when the player touches the selected object.</li><li><strong>Other Object Touches</strong>: Resets the timer when another object touches the selected object.</li><li><strong>Clicked</strong>: Resets the timer when you click the selected object.</li><li><strong>Broadcast Listened</strong>: Resets the timer when it receives a broadcast</li></ul></td></tr><tr><td><mark style="color:blue;"><code>Broadcast</code></mark></td><td> Define a broadcast to be generated that can trigger other actions. The broadcast is sent when the timer is reset.</td></tr></tbody></table>

While there is no pre-built  T# Wrapper available to customize the Reset Timer Logic Template you can write your own code in T# to implement this logic from scratch.

### Load Scene

The Load Scene logic template enables you to transition from one game environment (scene)  to another, such as progressing from one level to the next or exploring a new area.&#x20;

To add the Load Scene logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Load Scene under the header "Game".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>Load Scene When</code></mark></td><td><p></p><p>Choose from this dropdown when to transition to a different scene:</p><ul><li><strong>Broadcast Listened</strong>: After the object receives a broadcast message.</li><li><strong>Player Touch</strong>: When the player touches the object.</li><li><strong>Other Object Touch</strong>: When another object touches the object.</li><li><strong>Clicked</strong>: When you click on the object.</li></ul></td></tr><tr><td><mark style="color:blue;"><code>Scenes to Load</code></mark></td><td>Click the + button to choose the next scene to load when the trigger condition is met. It displays a list of all available scenes in the game.</td></tr><tr><td><mark style="color:blue;"><code>Can Repeat Previous Level</code></mark></td><td>Toggle that specifies whether the player can repeat the previous level</td></tr></tbody></table>

While there is no pre-built  T# Wrapper available to customize the Load Scene Logic Template you can write your own code in T# to implement this logic from scratch.

### Random Level Selector

The Random Level Selector Logic Template allows you to randomly load a scene from a list of predefined scenes. It is different from the Load Scene Logic Template because here the scene is chosen randomly from a list of multiple scenes

To add the Random Level Selector logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Random Level Selector.
3. Drag and drop it onto the desired asset.

You can then tailor the following parameters in Advanced Mode to match your needs:

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><mark style="color:blue;"><code>When</code></mark></td><td><p></p><p>Select When to Load a Random Level from a dropdown<strong>:</strong></p><ul><li>On Game Start</li><li>On Broadcast Listened</li></ul></td></tr><tr><td><mark style="color:blue;"><code>Scenes</code></mark></td><td>Add a selection of scenes to randomly choose from for loading.</td></tr></tbody></table>

While there is no pre-built  T# Wrapper available to customize the Load Scene Logic Template you can write your own code in T# to implement this logic from scratch.

