# Kill Player

When the player contacts an object with the Kill Player behavior, the player is killed and respawns at the last checkpoint. This is useful when the player enters a danger zone or interacts with a hazardous object.

To add the Kill Player logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Kill Player under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                               | Description                                                                                                                                   |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`Play SFX`</mark>             | Choose a short chime to play when the player is killed                                                                                        |
| <mark style="color:blue;">`Play VFX`</mark>             | Choose a small visual effect to play on the object when the player is killed                                                                  |
| <mark style="color:blue;">`Broadcast On Respawn`</mark> | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player is killed.</p> |

### Accessing the Kill Player Template using T\#

You can access and modify its behaviour using the T# wrapper - [KillPlayerTemplate](../../coding-using-t/t-logic-template-wrappers.md#killplayertemplate)
