# Jump Pad

The Jump Pad boosts the player's jump height when attached to an asset. Upon touching an object with the Jump Pad behavior, the player's jump is elevated. After the jump action, the jump height is restored to the initial value.

| Parameters  | Type                                                                                                 |
| ----------- | ---------------------------------------------------------------------------------------------------- |
| Start Event | Interaction based triggers-  "Jump"                                                                  |
| Effects     | Visual or auditory effects (like - SFX,VFX), Change in player properties ,  Trigger another behavior |
| Type        | Independent                                                                                          |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Jump Pad behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Jump Pad behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Jump Pad**.

You can customize the below-mentioned parameters according to your requirements:

| Parameters     | Description                                                                                                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX       | Choose a sound effect to play when the player jumps                                                                                                                           |
| Play VFX       | Choose a visual effect to play when the player jumps                                                                                                                          |
| Jump Force     | Define the multiplier by which the existing jump height will be multiplied for that instance                                                                                  |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player jumps at an increased height.</code></p> |

{% hint style="info" %}
Your Jump Height should ideally be greater than 2 for the Jump Pad to work. Small jump height values will not lead to an increased jump height. You can find Jump Height in the Player Controller Drawer. Eg: A jump Height of 0.1 with a Jump Force of 10 will change the total jump height to 0.01 which is lower than the initial height.
{% endhint %}
