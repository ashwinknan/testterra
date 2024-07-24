# OR Gate

The Or Operator is used when you want an event to occur when either one of the defined events has taken place. When broadcasts are received from any event indicated in the Or Operator behavior, the behaviour will perform a particular action.

Example: When the player completes either of the two checkpoints and the operator receives a broadcast message from either of them, the next event scheduled by the behavour is triggered.

To add the OR Gate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select OR Gate under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are prerequisite for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received all broadcasts.</td></tr></tbody></table>

### Accessing the OR Gate Template using T\#

You can directly use conditionals in T# and do not need a wrapper to access thie logic template

