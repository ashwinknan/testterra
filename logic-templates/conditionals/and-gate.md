# AND Gate

The **AND** operator is used when you want an event to occur only after a specific number of other events have taken place. When broadcasts are received from all the events specified in the **AND** operator behavior, another broadcast is triggered.

For example, the player only wins the game if they complete both of the game's checkpoints. When the player reaches each checkpoint, a broadcast is sent to the behaviour. Once the behavior receives both broadcasts, the game will end.

To add the AND Gate logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select AND Gate under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Wait For (Listen for)</td><td>Choose the broadcasts which are prerequisite for the operator to do further tasks. You can choose broadcasts from the selection menu. </td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the behaviour has received all broadcasts.</td></tr><tr><td></td><td></td></tr></tbody></table>

### Accessing the AND Gate Logic Template using T\#

You can directly use conditionals in T# and do not need a wrapper to access thie logic template

