# Update Magnet

The Update Magnet behavior increases the player's magnetic range, allowing them to collect items from a larger radius compared to the initial specified range.

| Parameters  | Type                                                                                |
| ----------- | ----------------------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened             |
| Effects     | Change in Player properties, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                         |

You can customize the parameters according to the game's needs:

To add the Update Magnet behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Update Magnet behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Update Magnet.**

You can customize the below-mentioned parameters according to your requirements:

| Parameter          | Description                                                                                                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Change Magnet When | <p>Define the action that will trigger a change in the magnetic field. The actions could be:<br>- After a broadcast message received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></p> |
| Radius             | The amount defined will act as the updated radius                                                                                                                                                                                                                                        |
| Play SFX           | Choose a sound effect to play when the magnet range is updated                                                                                                                                                                                                                           |
| Play VFX           | Choose a visual effect to play when the magnet range is updated                                                                                                                                                                                                                          |
| Broadcast Data     | <p>Define a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the magnetic range is updated</p>                                                                                                                                             |
