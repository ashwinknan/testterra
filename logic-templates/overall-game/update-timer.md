# Update Timer

In the game, significant events such as completing tasks or defeating enemies can adjust the timer, adding bonus time or starting time-limited challenges. Conversely, mistakes or failures can reduce the time. The Update Timer template is used to handle these changes.

To add the Update Timer logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Update Timer under the header "Game".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="282">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td><p></p><p>Select a trigger from the dropdown to activate the logic template:</p><ul><li><strong>Player Touches</strong>: Resets the timer when the player touches the selected object.</li><li><strong>Other Object Touches</strong>: Resets the timer when another object touches the selected object.</li><li><strong>Clicked</strong>: Resets the timer when you click the selected object.</li><li><strong>Broadcast Listened</strong>: Resets the timer when it receives a broadcast</li></ul></td></tr><tr><td>Operation</td><td>Define the operator that will modify the timer. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td>Update By</td><td>The quantity specified in this context will determine the extent to which the timer is modified.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the timer value is updated.</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the timer value is updated.</td></tr><tr><td>Broadcast on Update</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the timer is updated.</td></tr><tr><td>Execute always</td><td>This toggle, when activated, will always execute this. When off, it will execute it only once.</td></tr></tbody></table>

## Accessing the Update Timer Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [UpdateTimerTemplate](../../coding-using-t/t-logic-template-wrappers.md#updatetimertemplate). &#x20;

