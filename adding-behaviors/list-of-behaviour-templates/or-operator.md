# Or Operator

We use the Or Operator when we want an event to occur when <mark style="color:purple;">`either`</mark> of the defined events has taken place. When broadcasts are received from <mark style="color:purple;">`any event indicated`</mark> in the Or Operator behavior template, the template will perform a particular action.

Example: When the player completes either of the two checkpoints and the operator receives a broadcast message from <mark style="color:purple;">`either`</mark> of them, the next event scheduled by the behavior template is triggered.

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize the behavior:

<table><thead><tr><th width="257">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts that are <mark style="color:yellow;">prerequisites</mark> for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the behaviour template has received either of the  broadcast messages.</code></td></tr><tr><td></td><td></td></tr></tbody></table>
