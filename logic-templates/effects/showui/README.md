# ShowUI

The ShowUI behavior allows the creator to display UI elements on the screen in response to player interactions with game objects.

To add the Show UI logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Show UI Animation under the header "Effects".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="236">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Show On</td><td><p></p><p>Choose from the following options in the dropdown menu for when the UI Needs to be displayed:</p><ol><li>On Game Start</li><li>On Player Touch</li><li>On Other Object Touch</li><li>On Click</li><li>On Broadcast: If selected, specify the broadcast to listen to.</li></ol></td></tr><tr><td>Animation</td><td>CHoose the animation for the UI element</td></tr><tr><td>Screen Position</td><td>Choose from the dropdown  the position of the UI element</td></tr><tr><td>UI Template</td><td>Select from a list of pre-available UI Templates</td></tr><tr><td>Animation Duration</td><td>Specify the duration of Animation in seconds</td></tr><tr><td>Show for</td><td>Specify the duration for which the UI must be displayed</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the UI is displayed</td></tr></tbody></table>



Terra Studio has pre-defined UI Templates as shown in [`ShowUI Prefabs`](showui-prefabs.md).&#x20;
