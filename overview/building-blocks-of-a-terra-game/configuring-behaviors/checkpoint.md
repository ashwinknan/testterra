# Checkpoint

A checkpoint is a designated spot where player progress is saved automatically or manually. These markers allow you to restart the game from that specific point if you fail a challenge, lose a life, or need to pause the game.

| Parameters  | Type                                                                                                                                                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | Player crosses the checkpoint99                                                                                                                                                                                                             |
| Effects     | Change in Player or Asset properties, Change in Game Scene Environment, Change in Game Systems, Change in an Asset's Orientation, Create or Elimination existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                                                                                                                                                 |

To add the Checkpoint behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Checkpoint behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Checkpoint.**

You can customize the below-mentioned parameters according to your requirements:

| Parameter     | Description                                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX      | Choose a short chime to play when you arrive at checkpoint                                                                                                |
| Play VFX      | Choose a visual effect to play when you arrive at the checkpoint                                                                                          |
| BroadcastData | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the you arrive at the checkpoint.</p> |
