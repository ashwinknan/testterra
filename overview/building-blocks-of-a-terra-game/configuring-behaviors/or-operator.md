# Or Operator

The Or Operator is used when you want an event to occur when either one of the defined events has taken place. When broadcasts are received from any event indicated in the Or Operator behavior, the behaviour will perform a particular action.

Example: When the player completes either of the two checkpoints and the operator receives a broadcast message from either of them, the next event scheduled by the behavour is triggered.

| Parameters  | Type                        |
| ----------- | --------------------------- |
| Start Event | broadcast listened          |
| Effects     | Generate a Broadcast Signal |
| Type        | joiner                      |

To add the Or operator  behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Or operator  behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Or operator** **.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts that are prerequisites for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received either of the  broadcast messages.</td></tr><tr><td></td><td></td></tr></tbody></table>
