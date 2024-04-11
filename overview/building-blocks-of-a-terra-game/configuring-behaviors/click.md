# Click

The Click behavior enables you to send a broadcast when you click on an asset. Here are a few use cases for this behavior:

* **Puzzle Mechanics:** Assets can be incorporated into puzzle mechanics where clicking on one asset affects others. For example, clicking on a lever may activate a series of platforms or unlock a hidden passage.
* **Interactive Assets:** Clicking on assets triggers events or interactions, enhancing player engagement and immersion. For instance, clicking on a door may cause it to open or close.

&#x20;

| Parameters  | Type                                                                                                                             |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | Interaction based triggers- "mouse clicks"                                                                                       |
| Effect      | Visual or auditory effects (like - SFX,VFX ), Change in game systems (like change in score),Trigger another behavior (broadcast) |
| Type        | Independent                                                                                                                      |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Click behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Click behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Click**.

You can customize the below-mentioned parameters according to your requirements:

| Parameter      | Description                                                                                                                                     |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX       | Choose a sound effect to play when you click on the asset                                                                                       |
| Play  VFX      | Choose a visual effect to play when you click on the asset                                                                                      |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when you click on the asset.</p> |
