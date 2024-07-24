# Reset Timer

The Reset Timer behavior resets the game timer to its initial value without affecting the game experience. If it's a countdown timer, the time is reset to the starting value. If it's a count-up timer, the time is reset to 0 seconds.

You can customize the template parameters according to the game requirements:

To add the Reset Timer logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Reset Timer under the header "Game".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Reset When</td><td><p>Select a trigger from the dropdown to activate the logic template:</p><ul><li><strong>Player Touches</strong>: Resets the timer when the player touches the selected object.</li><li><strong>Other Object Touches</strong>: Resets the timer when another object touches the selected object.</li><li><strong>Clicked</strong>: Resets the timer when you click the selected object.</li><li><strong>Broadcast Listened</strong>: Resets the timer when it receives a broadcast</li></ul></td></tr><tr><td>Broadcast</td><td> Define a broadcast to be generated that can trigger other actions. The broadcast is sent when the timer is reset.</td></tr></tbody></table>

## Accessing the Reset Timer Template using T\#

There is currently no T# wrapper available for the Reset Timer Template.&#x20;
