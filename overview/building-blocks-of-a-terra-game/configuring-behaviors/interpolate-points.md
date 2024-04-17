# Interpolate Points

Using the Interpolate Points, objects can move along a specified path defined by coordinates. This movement can be either linear between points or curved, offering versatile motion options.&#x20;

Additionally, objects can dynamically rotate to ensure a particular face of the object always faces the direction of the path, similar to how our face naturally aligns with our direction of movement

| Parameters  | Type                                                                                            |
| ----------- | ----------------------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened             |
| Effects     | Change in Game Scene Environment, Change in an Asset's Orientation, Generate a Broadcast Signal |
| Type        | Independent                                                                                     |

To add the Interpolate Points behavior to an asset, follow these steps:

{% embed url="https://www.loom.com/share/23fb779803cd444d98f47df7d8fbebee?sid=1c587de4-6710-40e9-b0fb-a7fad42e52b4" %}
Interpolate Points&#x20;
{% endembed %}

1. Select the asset you wish to apply the Interpolate Points behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Interpolate Points.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="290">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Move On</td><td><p>You can define the trigger that will activate behaviour<br>- When the game starts </p><p>- When a different object touches the object<br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When the object is clicked </p></td></tr><tr><td>Points</td><td>You can define multiple points through which the object will move in a path</td></tr><tr><td>Speed</td><td>You can define the speed of object movement</td></tr><tr><td>Turn To Points</td><td>This one makes sure that  only one face on the object faces the forward direction. The orientation of the object changes such that one particular face/side of the object is facing forward throughout the whole movement.</td></tr><tr><td>Delay at Point</td><td>This gives a gap of  a few seconds before the object changes direction of motion. The object is stationary   during those few seconds.</td></tr><tr><td>Loop</td><td>If you check this, the movement is repeated until the template is deactivated</td></tr><tr><td>Is Curve</td><td>Changes the linear mobility path of the object to a  curved one.</td></tr><tr><td>Interpolate Types</td><td>You can choose between two types of movements:<br>- One direction: The object moves along the path in only forward motion<br>- Ping Pong: The object moves along the path in a back-and-forth motion</td></tr><tr><td>Broadcast Type</td><td><p>You can choose the instances when a broadcast will be sent. There are three options to choose from:</p><ul><li>Never - No broadcast to be sent</li><li>End - Send a broadcast after completing one whole movement from the start to the endpoint</li><li>At Every Pause - Send a broadcast every time the object pauses</li></ul></td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent on the above mentioned instances.</td></tr></tbody></table>
