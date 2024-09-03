# Effects

## Overview

<table><thead><tr><th width="263">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="effects.md#stop-rotate">Stop Rotate</a></td><td>Stops Rotation </td></tr><tr><td><a href="effects.md#showui">ShowUI</a></td><td>Displays a UI on the screen</td></tr><tr><td><a href="effects.md#stop-animation">Stop Animation</a></td><td>Stops Animation </td></tr><tr><td><a href="effects.md#play-players-animation">Play Player's Animation</a></td><td>Plays animation of the player</td></tr></tbody></table>

## List of Effects Logic Components

### Stop Rotate

Stop Rotate allows you to stop the rotation of any object by attaching the behaviour to it and defining any trigger to initiate the event.

| Parameters  | Type                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |
| Start Event | other object touches, mouse clicked, broadcast listened                                  |
| Effects     | Change in an Asset's Orientation, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | dependent                                                                                |

To add the Stop Rotate behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Stop Rotate behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Stop Rotate.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="268">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>StopWhen</td><td>You can choose the trigger on which the object will stop rotating. These are:<br>- After a broadcast message has been received by the object.<br>- When a different object touches the object<br>- When you click on the object.<br></td></tr><tr><td>Broadcast Data</td><td>Define a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when object stops rotating</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the object stops rotating.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the object stops rotating.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template but you can write your own custom T# code from scratch.&#x20;

### Stop Animation

The Stop Animation logic template is used for animated objects. When executed, it halts the current animation of the object.

To add the Stop Animation logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Stop Animation under the header "Effects".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Stop When</td><td><p></p><p>Choose from the following options in the dropdown menu for when the animation should be stopped:</p><ol><li>On Player Touch</li><li>On Other Object Touch</li><li>On Click</li><li>On Broadcast: If selected, specify the broadcast to listen to.</li></ol></td></tr><tr><td>Broadcast</td><td>Enter a broadcast to be generated at the end of execution. This broadcast can be used as a trigger for other behaviors.</td></tr></tbody></table>

There are currently no available T# Wrappers for this template.

### Play Player's Animation

The Play Player's animation logic template activates a predefined player animation when the trigger condition is met.

To add the Play Player's Animation logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Play Player's Animation under the header "Effects".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Play On</td><td><p></p><p>Choose from the following options in the dropdown menu for when the Player animation should Start:</p><ol><li>On Game Start</li><li>On Player Touch</li><li>On Other Object Touch</li><li>On Click</li><li>On Broadcast: If selected, specify the broadcast to listen to.</li></ol></td></tr><tr><td>Broadcast</td><td>Enter a broadcast to be generated at the end of execution. This broadcast can be used as a trigger for other behaviors.</td></tr><tr><td>Animation</td><td>Select an animation for the player to execute from the dropdown list</td></tr><tr><td>Reset Automatically</td><td>Toggle button that specifies whether the player animation must reset</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [PlayPlayerAnimationTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#playplayersanimationtemplate). You may also find the wrapper - [PlayerAnimationControlTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#playeranimationcontroltemplate) useful

### ShowUI

The ShowUI behavior allows the creator to display UI elements on the screen in response to player interactions with game objects.

To add the Show UI logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Show UI Animation under the header "Effects".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="236">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Show On</td><td><p></p><p>Choose from the following options in the dropdown menu for when the UI Needs to be displayed:</p><ol><li>On Game Start</li><li>On Player Touch</li><li>On Other Object Touch</li><li>On Click</li><li>On Broadcast: If selected, specify the broadcast to listen to.</li></ol></td></tr><tr><td>Animation</td><td>CHoose the animation for the UI element</td></tr><tr><td>Screen Position</td><td>Choose from the dropdown  the position of the UI element</td></tr><tr><td>UI Template</td><td>Select from a list of pre-available UI Templates</td></tr><tr><td>Animation Duration</td><td>Specify the duration of Animation in seconds</td></tr><tr><td>Show for</td><td>Specify the duration for which the UI must be displayed</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the UI is displayed</td></tr></tbody></table>



Terra Studio has pre-defined UI Templates as shown in [`ShowUI Prefabs`](broken-reference).&#x20;

ShowUI offers a wide selection of pre-defined UI layouts that can be used to display a UI in your game. You can choose any UI from the dropdown menu under "UI To Show." The name and layout of each UI are provided in the "Available UI Prefabs" table below. Each layout contains two types of elements:

* **Editable Text**: You can include up to three text elements—Text 1, Text 2, and Text 3. You can directly input the desired text in these fields.
* **Icons**: You can use up to two icons—Icon 1 and Icon 2. To access or modify an icon, simply input the icon's name from the list of available Show UI Icons

