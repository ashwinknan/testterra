# Debris Destructible

The Debris Destructible Behavior is employed to annihilate objects within the game environment. Upon destruction, this behavior generates debris or remnants linked to the destroyed object.

You can tailor the destruction process by defining various parameters, such as the force propelling the debris in the opposite direction, the delay before debris generation, and other relevant factors.

The debris resulting from destruction is defined using the Debris Behavior. Thus, both behaviors, Debris Destructible and Debris, are interconnected.

This integration fosters a dynamic and immersive destruction sequence, augmenting the realism and immersion of the game world.

| Parameters  | Type                                                                                           |
| ----------- | ---------------------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened                        |
| Effect      | Eliminates existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                    |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Debris Destructible behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Debris Destructible behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Debris Destructible**.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="291">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the asset.</p><p>- When a different object touches the asset having the behaviour<br>- After a broadcast message has been received by the asset.<br>- When the player collides with the asset<br>- When the object is clicked.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Add Delay</td><td>This adds a delay between the destruction and the trigger action in seconds.</td></tr><tr><td>Debris Group</td><td>This defines the debris that is the aftermath of destruction. The group is defined in the Debris behavior.</td></tr><tr><td>Debris Radius</td><td>Specify the radius within which the debris will scatter.</td></tr><tr><td>Debris Quantity</td><td>This is the total number of debris asset that will appear after destruction.</td></tr><tr><td>User Physics</td><td>When the "User Physics" property is unchecked, debris flies and disappears, but when checked, debris rolls around its edges before disappearing.</td></tr><tr><td>Force</td><td>Define the force by which the debris will scatter on the plane</td></tr><tr><td>Destroy Time</td><td>The total duration for which the debris will be present on the scene</td></tr></tbody></table>

