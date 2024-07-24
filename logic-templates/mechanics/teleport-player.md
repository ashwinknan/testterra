# Teleport Player

&#x20;The Teleport Player logic template can be used to teleport the player from one location to another in response to a specified trigger.

To add the Teleport Player logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Teleport Player under the header "Mechanics".
3. Drag and drop it onto the desired asset.

{% embed url="https://www.loom.com/share/ef35d82e57cc4b218fb7ac9f1e50a084?sid=4346d208-40a5-4909-a0ff-cd6db2aa12f0" %}
Teleport Player Behaviour
{% endembed %}

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Teleport When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</p></td></tr><tr><td>Teleport </td><td>You can choose the coordinates where you want the player to be teleported.</td></tr><tr><td>Loop-able</td><td>This allows you to loop the movement of the object. It appears as if it is oscillating between 2 different points.</td></tr><tr><td>Interval</td><td>Intervals add a delay between the back-and-forth movement of the object during the loop.</td></tr><tr><td>Move By</td><td>You can define how many units and in what axis the object will move</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play when the object starts to move</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play when the object starts to move</td></tr><tr><td>Broadcast </td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the object stops moving..</td></tr></tbody></table>

### Accessing the Teleport Player Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [TeleportTemplate](../../coding-using-t/t-logic-template-wrappers.md#teleporttemplate)
