# And Operator

The **AND** operator is used when you want an event to occur only after a specific number of other events have taken place. When broadcasts are received from all the events specified in the **AND** operator behavior, another broadcast is triggered.

For example, the player only wins the game if they complete both of the game's checkpoints. When the player reaches each checkpoint, a broadcast is sent to the behaviour. Once the behavior receives both broadcasts, the game will end.

| Parameters  | Type                        |
| ----------- | --------------------------- |
| Start Event | broadcast listened          |
| Effects     | Generate a Broadcast Signal |
| Type        | joiner                      |

To add the And operator  behavior to an asset, follow these steps:

{% embed url="https://www.loom.com/share/cb6ca67ff3ca4c0cbb8c386289411a90?sid=f36b693e-7485-4dff-a49b-c7b51faacc01" %}
And Operator&#x20;
{% endembed %}

1. Select the asset you wish to apply the And operator  behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **And operator** **.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are prerequisite for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received all broadcasts.</td></tr><tr><td></td><td></td></tr></tbody></table>



