# Load New Scene

Load New Scene template allows you to transition from one game environment to another, such as moving from one level to the next or entering a different area.&#x20;

The template is attached to an <mark style="color:yellow;">object</mark> which will trigger the change.

It can also be used for <mark style="color:purple;">cinematic sequences</mark>, <mark style="color:purple;">menu screens</mark>, or any other major change in the game's environment or gameplay.

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

You can customize:

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Load Scene When</td><td>Choose when to transition to a different scene. You can transition <br>- After a broadcast message has been received by the <mark style="color:yellow;">object</mark><br>- When the player touches the <mark style="color:yellow;">object</mark><br>- When a different object touches the <mark style="color:yellow;">object</mark><br>- When you click on the <mark style="color:yellow;">object</mark></td></tr><tr><td>Scenes to Load</td><td>From the drop-down list, you can choose <mark style="color:yellow;">which scene</mark> should play <mark style="color:yellow;">after the current scene</mark>.</td></tr></tbody></table>
