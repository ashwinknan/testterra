# Delay

The delay behaviour allows you to add a few seconds of delay in between the broadcasts which eventually creates a gap of a few seconds between two different events. Usually, events happen instantly as soon as they receive the broadcast but with the help of a delay behavior, you can add a delay between two events.

| Parameters  | Type                                                |
| ----------- | --------------------------------------------------- |
| Start Event |                                                     |
| Effects     | Change in Game Systems, Generate a Broadcast Signal |
| Type        | Independent                                         |

To add the Delay behavior to an asset, follow these steps:

1. Select the asset you wish to apply the delay behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Delay.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Listen To</td><td>Choose a broadcast from the drop drop menu. Once the object receives this broadcast, there will be a delay created for the next event.</td></tr><tr><td>Delay Time</td><td>Define the seconds by how long there will be a delay</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent after the defined delay time has completed.</td></tr></tbody></table>
