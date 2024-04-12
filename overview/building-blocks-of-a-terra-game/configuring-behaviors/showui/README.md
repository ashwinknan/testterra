# ShowUI

The ShowUI behavior allows the creator to display UI elements on the screen in response to player interactions with game objects.

| Parameters  | Type                                                                                |
| ----------- | ----------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened |
| Effects     | Display UI elements, Generate a Broadcast Signal                                    |
| Type        | Independent                                                                         |

To add the ShowUI behavior to an asset, follow these steps:

1. Select the asset you wish to apply the ShowUI behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **ShowUI.**

Terra Studio has pre-defined UI as shown below.

**`Step 1`**`:` First you select any asset as a Check-point and add the `ShowUI` Behaviour to it by clicking OK.

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-03-01 at 10.05.21 AM.png" alt="" width="185"><figcaption></figcaption></figure>

**`Step 2:`** Scroll down the inspector panel to see the ShowUI behaviour parameters.&#x20;

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-03-01 at 10.56.54 AM.png" alt="" width="298"><figcaption><p>All editable parameters in ShowUI</p></figcaption></figure>

`Step 3:` First click on Show On to select the trigger for the UI. There are four possible triggers available currently.&#x20;

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-03-01 at 10.06.12 AM.png" alt="" width="153"><figcaption><p>The possible triggers for a ShowUI Behavior</p></figcaption></figure>

**Step 3**: After selecting the trigger, decide on an animation and position of the UI. Then you need to select UI to Show and then enter the name of the icons & editable text. These names and layouts are available in [`ShowUI Prefabs`](showui-prefabs.md).&#x20;

**`Step 4`**`:` Finally select the Animation Time , Display Time and any Broadcast you may want to do and save the UI.&#x20;

**`Step 5`**`:` Play test and see if the UI is appearing as per your plan.&#x20;
