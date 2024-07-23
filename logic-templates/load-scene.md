# Load Scene

The Load Scene behavior enables you to transition from one game environment to another, such as progressing from one level to the next or exploring a new area. This behavior is linked to an object that initiates the transition when triggered.

It can also be utilized for cinematic sequences, menu screens, or any other significant change in the game's environment or gameplay.

| Parameters  | Type                                                                    |
| ----------- | ----------------------------------------------------------------------- |
| Start Event | player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Change in Game Scene Environment                                        |
| Type        | Independent                                                             |

To add the Load Scene behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Load Scene behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Load Scene.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Load Scene When</td><td>Choose when to transition to a different scene. You can transition <br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</td></tr><tr><td>Scenes to Load</td><td>From the drop-down list, you can choose which scene should play after the current scene.</td></tr></tbody></table>
