# Tick

Applying tick behavior to an asset allows you to attach a custom timer, whose start and stop can be controlled. This behavior can be used as a starting event for other behaviors.

| Parameters  | Type                           |
| ----------- | ------------------------------ |
| Start Event | game start, broadcast listened |
| Effects     | Generate a Broadcast Signal    |
| Type        | Independent                    |

To add the Tick behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Tick behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Tick.**

You can customize the below-mentioned parameters according to your requirements:\


<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Tick When</td><td>You can choose the start event on which the object will start rotating.<br>- It can be at the start of the game<br>- After a broadcast message has been received by the object.<br></td></tr><tr><td>Stop When</td><td>You can choose which trigger will stop the movement. Those can be:<br>- After a broadcast message has been received by the object.</td></tr><tr><td>Resume When</td><td>You can choose which trigger will resume the movement. Those can be:<br>- After a broadcast message has been received by the object.</td></tr></tbody></table>
