# Collectable

A Collectible is a logic template added to an asset in a game that can be collected to increase score or to achieve another goal.

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Collectable logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Collectable under the header "Mechanics".
3. Drag and drop it onto the desired asset.

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

### Accessing the Collectible Template using T\#

You can access this using the T# Wrapper - [CollectableTemplate](../../coding-using-t/t-logic-template-wrappers.md#collectabletemplate)
