# Update Score

You may want to enhance the gameplay experience by adjusting the game [score ](../setting-up-game-systems/#score)when specific conditions are met. For instance:

* Update the score when the player collects items such as coins, gems, or power-ups. This promotes exploration and rewards the player's curiosity.
* Increase the score upon completing a level or reaching a milestone, such as finishing a race track or solving a puzzle.
* Award points for unique or challenging achievements outside the normal gameplay loop, such as discovering hidden areas.

In these situations, you can use the Update Score behavior.

| Parameters  | Type                                                                    |
| ----------- | ----------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Change in Game Systems, Generate a Broadcast Signal                     |
| Type        | Independent                                                             |

To add the Update Score behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Update Score behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Update Score.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for updating the score. There are four triggers allowed:<br>Player Touches- Updates the score when the player touches the selected object<br>Other Object Touches - Updates the score when another object touches the selected object<br>Clicked - Updates the score when you click the selected object<br>Broadcast Listened - Updates the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be updated based on the trigger event happening</td></tr><tr><td>Operator </td><td>Define the operator to multiply by. Four operators are allowed - Add, Subtract, Multiply and Divide</td></tr><tr><td>Update By</td><td>Define an integer (positive or negative) to change the score by. For instance, if the operator is Add and Update By is given the value 10, then the score is increased by 10 every time the trigger event defined in Update When happens</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

