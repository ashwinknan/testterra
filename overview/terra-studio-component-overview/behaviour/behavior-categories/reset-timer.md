# Reset Timer

The Reset Timer template resets the game timer to the initial value without altering the game experience. If it is a countdown timer, the time is reset back to the initial value and if it is a count-up value, the time is reset back to 0 seconds.

You can customize the template parameters according to the game requirements:

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Reset When</td><td>This parameter helps you define the trigger that will activate the template. <br><mark style="color:purple;"><code>Player Touches</code></mark>- Resets the timer when the player touches the selected object<br><mark style="color:purple;"><code>Other Object Touches</code></mark> - Resets the timer when another object touches the selected object<br><mark style="color:purple;"><code>Clicked</code></mark> - Resets the timer when you click the selected object<br><mark style="color:purple;"><code>Broadcast Listened</code></mark> -Resets the timer when it listens to a broadcast from another object </td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the timer is reset</code></td></tr></tbody></table>

