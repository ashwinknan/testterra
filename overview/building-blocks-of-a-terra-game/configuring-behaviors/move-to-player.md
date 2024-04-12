# Move to Player

Objects with the MoveToPlayer behavior will leave their designated location and move towards the player. They track the player's movement and follow in the same direction. Multiple triggers can activate this behavior as needed.

| Parameters  | Type                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened                  |
| Effects     | Change in an Asset's Orientation, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                              |

To add the Move to player behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Move to player behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Move to player.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="306">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>MoveToPlayerWhen</td><td>You can choose the trigger to activate the behaviour<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>MoveSpeed</td><td>You can fix the speed for object movement</td></tr><tr><td>Offset</td><td>Specifying offset value ensures that the object will move a specific number of units in the given axis. It won't follow you but will relocate to a different location on triggering.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Cancel On</td><td>You can choose when to stop the movement of the object.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.</td></tr><tr><td>Cancel Type</td><td>You can choose what happens to the object once it stops moving. <br>- It can relocate back to its original position.<br>- It can stop at the current position.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object comes in contact with you.</td></tr></tbody></table>

