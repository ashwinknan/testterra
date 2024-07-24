# Change Player Speed

Applying the Change Player Speed template changes the speed of the player to the desired value.&#x20;

To add the Change Player Speed logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Change Player Speed under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Change On When</td><td><p></p><p>Define the trigger for changing the speed. The four available triggers are:</p><ul><li><strong>Player Touches</strong></li><li><strong>Other Object Touches</strong></li><li><strong>Clicked</strong></li><li><strong>Broadcast Listened</strong></li></ul></td></tr><tr><td>Modifier</td><td>Define the modifier: <br>1. Set - Set to a defined value <br>2. Multiply - Multiply by the given value<br>3. Add - Increase by the given value<br>4. Subtract - Subtract the given value<br>5. Divide - Divide by the given value</td></tr><tr><td>Speed </td><td>Specify the value to apply the modifier to the current speed</td></tr><tr><td>SFX / VFX</td><td>Specify the SFX and VFX to be played upon execution</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

### Accessing the Change Player Speed Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [ChangePlayerSpeedTemplate](../../coding-using-t/t-logic-template-wrappers.md#changeplayerspeedtemplate)
