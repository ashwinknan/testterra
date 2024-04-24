# Self-service customer

Self-service customers are a distinctive behavior type frequently employed in Tycoon Games. They allow creators to simulate customer actions using NPC assets, particularly in self-service stores. For instance, applying the Self-service customer behavior to a "bunny" visiting a store to purchase 5 apples, 6 eggs, and 2 bananas would prompt the NPC to enter the store, locate the respective shelves, collect the desired items, proceed to the checkout counter for billing, and finally, complete the transaction to obtain the items.

| Parameters  | Type                                                                               |
| ----------- | ---------------------------------------------------------------------------------- |
| Start Event |                                                                                    |
| Effects     | Creates Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                        |

To add the Self-service customers behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Self-service customers behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Self-service customers.**

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
