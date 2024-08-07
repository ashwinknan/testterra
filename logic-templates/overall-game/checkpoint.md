# Checkpoint

A checkpoint is a designated spot where player progress is saved automatically or manually. These markers allow you to restart the game from that specific point if you fail a challenge, lose a life, or need to pause the game.

To add the checkpoint logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Checkpoint under the header "Game".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

| Parameter     | Description                                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX      | Choose a short chime to play when you arrive at checkpoint                                                                                                |
| Play VFX      | Choose a visual effect to play when you arrive at the checkpoint                                                                                          |
| BroadcastData | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the you arrive at the checkpoint.</p> |

## Accessing the Checkpoint Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [CheckpointTemplate](../../coding-using-t/t-logic-template-wrappers.md#checkpointtemplate).&#x20;
