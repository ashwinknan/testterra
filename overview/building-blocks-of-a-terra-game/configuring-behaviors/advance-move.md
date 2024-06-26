# Advance Move

The Advanced Move behavior builds upon the [Move ](move.md)behavior by offering additional features. With the Advanced Move feature, you can customize the type of motion, allowing for repeating patterns and continuous motion indefinitely.

| Parameters  | Type                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened      |
| Effects     | Change in an Asset's Orientation, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                              |

To add the Advance Move behavior to an asset, follow these steps:

1. Select the asset you wish to apply the  Advance Move behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Advance Move.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Move When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</p></td></tr><tr><td>Move By</td><td>You can define how many units and in what axis the object will move</td></tr><tr><td>Speed</td><td>You can define the speed of the object</td></tr><tr><td>Repeat</td><td>You can set the number of times the motion repeats</td></tr><tr><td>Repeat forever </td><td>checkbox that will help to repeat the same motion in loop</td></tr><tr><td>Pause for</td><td>The duration of the pause between each cycle of motion can be adjusted</td></tr><tr><td>Repeat type </td><td>You can use this option to select the type of motion<br>There are two types motion the behaviour supports at the moment <br>1. Ping Pong<br>2. Same Direction </td></tr><tr><td>Broadcast when</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving.</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr></tbody></table>
