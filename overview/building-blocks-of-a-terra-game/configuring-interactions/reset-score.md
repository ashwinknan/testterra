# Reset Score

You might want to enhance the gameplay experience by resetting the game score to zero when certain conditions are met during gameplay. For example, you may choose to reset the score when the player starts a new game or advances to a new level.

In such cases, Reset Score behaviour is used.

| Parameters  | Type                                                                    |
| ----------- | ----------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Change in Game Systems, Generate a Broadcast Signal                     |
| Type        | Independent                                                             |

To add the Reset Score behavior to an asset, follow these steps:

1. Select the asset you wish to apply the  Reset Score behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Reset Score.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for resetting the score. There are four triggers allowed:<br>Player Touches- Resets the score when the player touches the selected object<br>Other Object Touches - Resets the score when another object touches the selected object<br>Clicked - Resets the score when you click the selected object<br>Broadcast Listened - Resets the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be reset based on the trigger event happening</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

