# List of Behaviour Templates

{% hint style="info" %}
This section is Work in Progress. Expect more details about each behaviour template soon.
{% endhint %}

Terra Studio currently supports the following behaviour templates:

| Behaviour Template                                    | What it Achieves                                                  |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| [`Collectable`](collectable.md)                       | Collect this item and add / subtract points to your score         |
| [`Kill Player`](kill-player.md)                       | Kills a player instantly                                          |
| `Teleport`                                            | Instantly moves the player to a defined position                  |
| `Destroy`                                             | Eliminates the object from the scene upon interaction             |
| `Rotate`                                              | Adds rotational movement to the object                            |
| [`Move`](move.md)                                     | Adds linear movement to the object                                |
| `Switch`                                              | Creates an "On" and "Off" State                                   |
| `Click`                                               | Broadcasts when the object is clicked                             |
| [`Collide`](collide.md)                               | Broadcasts when the object is collided with                       |
| `Update Timer`                                        | Adds / subtracts defined seconds to the game timer                |
| [`Update Player Score`](update-player-score.md)       | Adds / subtracts defined to the player's score                    |
| `Reset Timer`                                         | Resets timer to the original defined time                         |
| [`Reset Player Score`](reset-player-score.md)         | Resets the player’s score to 0                                    |
| `Instantiate`                                         | Create instance(s) of the object at different times and/or areas  |
| [`Increase Player Health`](increase-player-health.md) | Adds to player health                                             |
| [`Decrease Player Health`](decrease-player-health.md) | Damages or reduces player health                                  |
| [`Reset Player Health`](reset-player-health.md)       | Resets player health to full                                      |
| [`Checkpoint`](checkpoint.md)                         | Save state for player progress in-game                            |
| Level Up                                              | Alters object properties as game progresses                       |
| [`Load New Scene`](load-new-scene.md)                 | Triggers scene change                                             |
| [`Start Player Movement`](start-player-movement.md)   | Player is allowed to move in the environment                      |
| [`Stop Player Movement`](stop-player-movement.md)     | Player movement is blocked                                        |
| [`Move to Player`](move-to-player.md)                 | Objects move towards the player                                   |
| Update Magnet                                         | Updates magnet range of the player                                |
| Jump Pad                                              | Triggers a jump movement                                          |
| Show UI                                               |                                                                   |
| [`And Operator`](and-operator.md)                     | Requires all of the mentioned broadcasts to trigger the event     |
| [`Or Operator`](or-operator.md)                       | Requires any one of the mentioned broadcasts to trigger the event |



