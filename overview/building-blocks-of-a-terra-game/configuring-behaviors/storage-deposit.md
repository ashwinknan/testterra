# Storage deposit

Storage deposit are a distinct type of behavior frequently employed in Tycoon Games. They grant creators the ability to assign behaviors to assets, allowing act as a storage units or selves of a paticalar kind of asset. For instance, by applying the Storage deposit behavior to a "store selves of a grocery store," it gains the capability to store a paticular kind of grocery item.

| Parameters  | Type                                                                               |
| ----------- | ---------------------------------------------------------------------------------- |
| Start Event |                                                                                    |
| Effects     | Creates Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                        |

To add the Storage deposit behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Converter behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Storage deposit.**

You can customize the below-mentioned parameters according to your requirements:

| Parameter               | Description                                                                                                                                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Collect When            | <p></p><p>Choose when the item is “collected”:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Sound Effect on Start   | Choose a short chime to play when item is collected                                                                                                                                                                   |
| Visual Effect on Start  | Choose a small visual effect to play when item is collected                                                                                                                                                           |
| Score Group             | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                          |
| Update Score By         | <p>Enter a numerical score value to update when collected.<br>✨ Note: to reduce a score when collected, enter a negative value!</p>                                                                                   |
| IsMultiLevel            | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                     |
| Broadcast On Collection | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                         |
