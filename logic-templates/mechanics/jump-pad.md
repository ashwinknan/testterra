# Jump Pad

The Jump Pad boosts the player's jump height when attached to an asset. Upon touching an object with the Jump Pad logic template, the player's jump is elevated. After the jump action, the jump height is restored to the initial value.

To add the Jump Pad logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Jump Pad under the header "Mechanics".
3. Drag and drop it onto the desired asset.

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

### Accessing the Jump Pad Template using T\#

You can use the T# Wrapper - [JumpPadTemplate](../../coding-using-t/t-logic-template-wrappers.md#jumppadtemplate)
