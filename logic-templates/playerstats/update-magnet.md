# Update Magnet

The Update Magnet behavior increases the player's magnetic range, allowing them to collect items from a larger radius compared to the initial specified range.

To add the Update Magnet logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Update Magnet under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

| Parameter          | Description                                                                                                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Change Magnet When | <p>Define the action that will trigger a change in the magnetic field. The actions could be:<br>- After a broadcast message received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.<br></p> |
| Radius             | The amount defined will act as the updated radius                                                                                                                                                                                                                                        |
| Play SFX           | Choose a sound effect to play when the magnet range is updated                                                                                                                                                                                                                           |
| Play VFX           | Choose a visual effect to play when the magnet range is updated                                                                                                                                                                                                                          |
| Broadcast Data     | <p>Define a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the magnetic range is updated</p>                                                                                                                                             |

### Accessing the Update Magnet Animation Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [ChangeMagnetTemplate](../../coding-using-t/t-logic-template-wrappers.md#changemagnettemplate)
