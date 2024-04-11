# Update Timer

In the game, significant events like completing tasks or defeating enemies may trigger adjustments to the timer, adding bonus time, or initiating time-limited challenges. Conversely, mistakes or failures can lead to time deductions.

All of the above can be done using the Update Timer Template.

You can customize the template parameters according to the game requirements:

<table><thead><tr><th width="282">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td><p>This parameter helps you define the trigger that will activate the template. <br><mark style="color:purple;"><code>Player Touches</code></mark>- Updates the timer when the player touches the selected object</p><p><mark style="color:purple;"><code>Other Object Touches</code></mark> - Updates the timer when another object touches the selected object</p><p><mark style="color:purple;"><code>Clicked</code></mark> - Updates the timer when you click the selected object</p><p><mark style="color:purple;"><code>Broadcast Listened</code></mark> - Updates the timer when it listens to a broadcast from another object </p></td></tr><tr><td>Operation</td><td>Define the operator that will modify the timer. Four operators are allowed - <mark style="color:purple;"><code>Add,</code></mark> <mark style="color:purple;"><code>Subtract</code></mark>, <mark style="color:purple;"><code>Multiply</code></mark> and <mark style="color:purple;"><code>Divide</code></mark></td></tr><tr><td>Update By</td><td>The quantity specified in this context will determine the extent to which the timer is modified.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the timer value is updated.</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the timer value is updated.</td></tr><tr><td>Broadcast on Update</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the timer is updated.</code></td></tr><tr><td>Execute once</td><td>This restricts the timer to update more than once during the game play.</td></tr></tbody></table>