# Jump Pad

The Jump Pad behavior template multiplies the jump height of the player. When you come in contact with this behavior attached to an object, you jump at an increased height. After the jump action, the jump height is `restored` to the `initial value.`\
\
So, `every time` you collide with an object containing Jump Pad behavior, you will jump at an increased height.\
\
To add Jump Pad to an object:\
<mark style="color:yellow;">Step 1</mark>: Select the object

<mark style="color:yellow;">Step 2</mark>: Click on Add Behavior in the inspector panel, and select Jump Pad from the list of behaviors. You can customize the below-mentioned parameters according to your requirements:

| Parameters     | Description                                                                                                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Play SFX       | Choose a sound effect to play when the player jumps                                                                                                                           |
| Play VFX       | Choose a visual effect to play when the player jumps                                                                                                                          |
| Jump Force     | Define the multiplier by which the existing jump height will be multiplied for that instance                                                                                  |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the player jumps at an increased height.</code></p> |

{% hint style="info" %}
Your Jump Height should ideally be greater than 2 for the Jump Pad to work. Small jump height values will not lead to an increased jump height. You can find Jump Height in the Player Controller Drawer. Eg: A jump Height of 0.1 with a Jump Force of 10 will change the total jump height to 0.01 which is lower than the initial height.
{% endhint %}
