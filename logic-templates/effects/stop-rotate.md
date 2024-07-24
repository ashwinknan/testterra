# Stop Rotate

Stop Rotate allows you to stop the rotation of any object by attaching the behaviour to it and defining any trigger to initiate the event.

| Parameters  | Type                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |
| Start Event | other object touches, mouse clicked, broadcast listened                                  |
| Effects     | Change in an Asset's Orientation, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | dependent                                                                                |

To add the Stop Rotate behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Stop Rotate behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Stop Rotate.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="268">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>StopWhen</td><td>You can choose the trigger on which the object will stop rotating. These are:<br>- After a broadcast message has been received by the object.<br>- When a different object touches the object<br>- When you click on the object.<br></td></tr><tr><td>Broadcast Data</td><td>Define a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when object stops rotating</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the object stops rotating.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the object stops rotating.</td></tr></tbody></table>
