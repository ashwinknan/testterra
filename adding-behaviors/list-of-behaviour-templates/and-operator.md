# And Operator

We use the And Operator when we want an event to occur <mark style="color:purple;">`only`</mark> after a specific number of other events have taken place. When broadcasts are received from <mark style="color:purple;">`every event`</mark> indicated in the And Operator behavior template, the template will perform a particular action.

Example: The player only wins the game if he completes both of the game's checkpoints. So here both the checkpoints will send a broadcast to the template when <mark style="color:red;">you reach those checkpoints</mark>. Once the behavior <mark style="color:red;">receives both broadcasts,</mark> the game will end.

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize the behavior:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are <mark style="color:yellow;">prerequisite</mark> for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the behaviour template has received all broadcasts.</code></td></tr><tr><td></td><td></td></tr></tbody></table>



