# Checkpoint

A checkpoint is a predetermined point where your progress is saved automatically or manually. These markers enable you to <mark style="color:purple;">resume your game</mark> from that specific point if you <mark style="color:purple;">fail a challenge</mark>, <mark style="color:purple;">lose a life</mark>, or <mark style="color:purple;">need to take a break</mark>.

| Parameters  | Type                                                                                                                                                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened                                                                                                                                                         |
| Effects     | Change in Player or Asset properties, Change in Game Scene Environment, Change in Game Systems, Change in an Asset's Orientation, Create or Elimination existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                                                                                                                                                 |

To add the Update Score behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Update Score behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Update Score.**

You can customize the below-mentioned parameters according to your requirements:

You can customise these parameters:

| Parameter     | Description                                                                                                                                                            |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX      | Choose a short chime to play when you arrive at checkpoint                                                                                                             |
| Play VFX      | Choose a visual effect to play when you arrive at the checkpoint                                                                                                       |
| BroadcastData | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the you arrive at the checkpoint.</code></p> |
