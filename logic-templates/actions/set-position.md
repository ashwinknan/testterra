# Set Position

The Set Position logic template enables you to specify the position of an asset.

To add the Set Position logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Set Position under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="452">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Set Position on</td><td><p>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Target</td><td>Specify the target destination position either by recording or entering the target coordinates in the fields X, Y and Z.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play on execution</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play on execution</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr></tbody></table>

### Accessing the Set Position Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper - [SetPositionTemplate](../../coding-using-t/t-logic-template-wrappers.md#setpositiontemplate)
