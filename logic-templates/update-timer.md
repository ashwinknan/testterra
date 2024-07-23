# Update Timer

In the game, significant events like completing tasks or defeating enemies may trigger adjustments to the timer, adding bonus time, or initiating time-limited challenges. Conversely, mistakes or failures can lead to time deductions.

All of the above can be done using the Update Timer Template.

| Parameters  | Type                                                                           |
| ----------- | ------------------------------------------------------------------------------ |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened        |
| Effects     | Change in Game Systems, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                    |

You can customize the template parameters according to the game requirements:

To add the Update Timer behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Instantiate behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Instantiate.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="282">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td><p>This parameter helps you define the trigger that will activate the behaviour. <br>Player Touches- Updates the timer when the player touches the selected object</p><p>Other Object Touches - Updates the timer when another object touches the selected object</p><p>Clicked - Updates the timer when you click the selected object</p><p>Broadcast Listened - Updates the timer when it listens to a broadcast from another object </p></td></tr><tr><td>Operation</td><td>Define the operator that will modify the timer. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td>Update By</td><td>The quantity specified in this context will determine the extent to which the timer is modified.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the timer value is updated.</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the timer value is updated.</td></tr><tr><td>Broadcast on Update</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the timer is updated.</td></tr><tr><td>Execute once</td><td>This restricts the timer to update more than once during the game play.</td></tr></tbody></table>
