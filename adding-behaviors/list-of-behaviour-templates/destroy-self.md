# Destroy Self

The destroy self template is used when you want to remove or destroy objects from the game scene on a certain trigger. The objects with this template are destroyed without any trace of them being there.

This template is very similar to the Collectable template, the only difference being that the Collectable contributes to a score group and this does not. In both templates, the object disappears after the trigger.

To add this behavior, follow these steps:&#x20;

* <mark style="color:yellow;">Step 1</mark>: Select the object or trigger to which you want to apply this template
* <mark style="color:yellow;">Step 2</mark>: Enter the following parameters to customize the behavior:

| Parameters     | Description                                                                                                                                                                                                                                                                                                                                                                                                    |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Destroy When   | <p>You can choose the trigger when to destroy the object.<br>- When the game starts</p><p>- When a different object touches the object having the template<br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark><br>- When the object is <mark style="color:yellow;">clicked</mark></p> |
| Play SFX       | Choose a sound effect to play when the object is destroyed.                                                                                                                                                                                                                                                                                                                                                    |
| Play VFX       | Choose a visual effect to play when the object is destroyed.                                                                                                                                                                                                                                                                                                                                                   |
| Broadcast Data | <p>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when the object is destroyed.</code></p>                                                                                                                                                                                                                                                  |
| Destroy After  | The time in seconds after which the object disappears from the scene.                                                                                                                                                                                                                                                                                                                                          |

