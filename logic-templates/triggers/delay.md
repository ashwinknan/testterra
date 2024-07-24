# Delay

The Delay logic template allows you to add a few seconds of delay in between the broadcasts which eventually creates a gap of a few seconds between two different events. Usually, events happen instantly as soon as they receive the broadcast but with the help of a delay behavior, you can add a delay between two events.

To add the Delay logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Delay under the header "Triggers".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Listen To</td><td>Choose a broadcast from the drop drop menu. Once the object receives this broadcast, there will be a delay created for the next event.</td></tr><tr><td>Delay Time</td><td>Define the seconds by how long there will be a delay</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after the defined delay time has completed.</td></tr></tbody></table>

### Accessing the Delay Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [DelayBroadcastTemplate](../../coding-using-t/t-logic-template-wrappers.md#delaybroadcasttemplate)

