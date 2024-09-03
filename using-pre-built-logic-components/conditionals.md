# Conditionals

## Overview

The table below shows a list of logic template components that can execute conditionals

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="conditionals.md#switch">Switch</a></td><td>Helps activate or deactivate behaviors depending on the triggers associated with each action. </td></tr><tr><td><a href="conditionals.md#or-gate">OR Gate</a></td><td>Acts as a gate that sends out a broadcast signal only after any one of the  required conditions are met. These conditions are broadcast signals from various sources. </td></tr><tr><td><a href="conditionals.md#and-gate">AND Gate</a></td><td>Acts as a gate that sends out a broadcast signal only after all required conditions are met. These conditions are broadcast signals from various sources. It won't activate until every condition is satisfied.</td></tr><tr><td><a href="conditionals.md#tick">Tick</a></td><td>Generates a broadcast at a pre-defined time or time-intervals</td></tr></tbody></table>

## List of all Conditional Logic Template Components

### Switch

The Switch logic template enables you to regulate the behaviors of an asset, whether it's the one you're interacting with or a different one. You can transmit broadcasts to activate or deactivate behaviors depending on the triggers associated with each action.&#x20;

For instance, suppose a cube possesses a switch logic template. In that case, when the player collides with the cube, an 'on-broadcast' signal is dispatched to the laser, prompting its rotation. Conversely, clicking on the cube sends an 'off-broadcast' signal to the laser, ceasing its rotation.

To add the Switch logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Switch under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="313">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Switch On</td><td><p>You can choose the trigger that will turn "on" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object.<br>- When the object is clicked </p></td></tr><tr><td>Sound Effect When On</td><td>Choose a sound effect to play when the switch is turned "on"</td></tr><tr><td>Visual Effect When On</td><td>Choose a visual effect to play when the switch is turned "on"</td></tr><tr><td>Broadcast After On</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "on"</td></tr><tr><td>Switch Off</td><td><p>You can choose the trigger that will turn "off" the switch:</p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object</p><p>-When the player exits.<br>- When the player collides with the object<br>- When the object is clicked</p></td></tr><tr><td>Sound Effect When Off</td><td>Choose a sound effect to play when the switch is turned "off"</td></tr><tr><td>Visual Effect When Off</td><td>Choose a visual effect to play when the switch is turned "off"</td></tr><tr><td>Broadcast After Off</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when switch is turned "off"</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [SwitchTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#switchtemplate)

### OR Gate

The Or Operator is used when you want an event to occur when either one of the defined events has taken place. When broadcasts are received from any event indicated in the Or Operator behavior, the behaviour will perform a particular action.

Example: When the player completes either of the two checkpoints and the operator receives a broadcast message from either of them, the next event scheduled by the behavour is triggered.

To add the OR Gate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select OR Gate under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are prerequisite for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received all broadcasts.</td></tr></tbody></table>

You can directly use conditionals in T# and do not need a wrapper to access this logic template

### AND Gate

The **AND** operator is used when you want an event to occur only after a specific number of other events have taken place. When broadcasts are received from all the events specified in the **AND** operator behavior, another broadcast is triggered.

To add the AND Gate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select AND Gate under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are prerequisite for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received all broadcasts.</td></tr></tbody></table>

You can directly use conditionals in T# and do not need a wrapper to access this logic template

### Tick

Applying the Tick Logic template to an asset allows you to customize a timer. Unlike the default timer, which you can only start or stop, this template lets you control or modify the start and stop functions. You can also pause the timer or send specific broadcasts at determined intervals. Additionally, this logic template can act as a starting event for other logic templates.

To add the Tick logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Tick under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:\


<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Tick When</td><td><p>You can choose the start event for the object's timer from this dropdown:</p><ul><li>Game Start</li><li>Broadcast Received: When the object receives a broadcast message.</li></ul><p><br></p></td></tr><tr><td>Stop When</td><td>You can choose which broadcast will stop the execution when listened to.</td></tr><tr><td>Resume When</td><td>You can choose which broadcast will resume the execution when listened to.</td></tr><tr><td>Special Broadcasts</td><td><p>You can specify time intervals for the template to run and generate a broadcast. The available fields are:</p><ul><li><strong>When</strong>: Select "At" or "Every".</li><li><strong>In</strong>: Specify the time interval for the broadcast.</li><li><strong>Broadcast</strong>: Define the broadcast to be generated.</li></ul></td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [TickTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#ticktemplate)
