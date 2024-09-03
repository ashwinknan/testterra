# Triggers

## Overview

Triggers are logic templates that initiate various game interactions. The table below describes the three main trigger logic templates:

<table><thead><tr><th width="262">Logic Template</th><th>Description</th></tr></thead><tbody><tr><td><a href="triggers.md#collide">Collide</a></td><td>Uses contact of collider of the player as a trigger and allows you to generate a broadcast</td></tr><tr><td><a href="triggers.md#click">Click</a></td><td>Uses mouse click as a trigger and allows you to generate broadcast</td></tr><tr><td><a href="triggers.md#delay">Delay</a></td><td>Introduces a delay of a specified time</td></tr></tbody></table>

## List of Trigger Logic Template Components

### Collide

Any object with the Collide logic template attached sends a broadcast either when you collide with it or when a different object touches it.

To add the Collide logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Collide under the header "Triggers".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="259">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start On</td><td>Choose how to collide. You have OnPlayerCollide or OtherObjectTouches</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when you collide with the object.</td></tr><tr><td>BroadcastData</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when you collide with the object.</td></tr></tbody></table>

### Click

The Click logic template enables you to send a broadcast when you click on an asset.&#x20;

To add the Click logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Click under the header "Triggers".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter      | Description                                                                                                                                     |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX       | Choose a sound effect to play when you click on the asset                                                                                       |
| Play  VFX      | Choose a visual effect to play when you click on the asset                                                                                      |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when you click on the asset.</p> |

### Delay

The Delay logic template allows you to add a few seconds of delay in between the broadcasts which eventually creates a gap of a few seconds between two different events. Usually, events happen instantly as soon as they receive the broadcast but with the help of a delay behavior, you can add a delay between two events.

To add the Delay logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Delay under the header "Triggers".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Listen To</td><td>Choose a broadcast from the drop drop menu. Once the object receives this broadcast, there will be a delay created for the next event.</td></tr><tr><td>Delay Time</td><td>Define the seconds by how long there will be a delay</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after the defined delay time has completed.</td></tr></tbody></table>

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [DelayBroadcastTemplate](../scripting-custom-logic-components/t-logic-component-template-wrappers.md#delaybroadcasttemplate)
