# Collectable

A Collectable is an item in a game that can be collected for an increase in score or towards another goal. This item can be collected when the player clicks on it in the scene, when they collide with it, when it is in magnet range, or when they have to stay near the Collectable for a specific amount of time.

| Type of trigger             | Triggers                                                             | Type of Outcome                                                                                                                            | Outcome                                                        |
| --------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------- |
| Interaction based triggers  | mouse clicks, player-asset collisions, On Trigger Stay, Magnet Range |  Application of visual or sound effects, Alterations to game systems, Creation or removal of entities, Activation of subsequent behaviors. | score increase, SFX,VFX, destruction of collection, broadcast  |

One or multiple triggers can be created, resulting in one or multiple outcomes.

For you to customize:

| Parameter               | Description                                                                                                                                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Collect When            | <p></p><p>Choose when the item is “collected”:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Sound Effect on Start   | Choose a short chime to play when item is collected                                                                                                                                                                   |
| Visual Effect on Start  | Choose a small visual effect to play when item is collected                                                                                                                                                           |
| Score Group             | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                          |
| Update Score By         | <p>Enter a numerical score value to update when collected.<br>✨ Hint: to reduce a score when collected, enter a negative value!</p>                                                                                   |
| IsMultiLevel            | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                     |
| Broadcast On Collection | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br><code>The broadcast is sent when the item is collected</code></p>                                                            |

