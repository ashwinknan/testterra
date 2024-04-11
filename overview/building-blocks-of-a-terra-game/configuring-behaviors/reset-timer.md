# Reset Timer

The Reset Timer behavior resets the game timer to its initial value without affecting the game experience. If it's a countdown timer, the time is reset to the starting value. If it's a count-up timer, the time is reset to 0 seconds.

| Parameters  | Type                                                                    |
| ----------- | ----------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Change in Game Systems, Generate a Broadcast Signal                     |
| Type        | Independent                                                             |

You can customize the template parameters according to the game requirements:

To add the Reset Timer behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Reset Timer  behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Reset Timer.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="318">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Reset When</td><td>This parameter helps you define the trigger that will activate the behaviour. <br>Player Touches- Resets the timer when the player touches the selected object<br>Other Object Touches - Resets the timer when another object touches the selected object<br>Clicked - Resets the timer when you click the selected object<br>Broadcast Listened -Resets the timer when it listens to a broadcast from another object </td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the timer is reset</td></tr></tbody></table>

