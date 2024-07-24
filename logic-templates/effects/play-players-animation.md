# Play Player's Animation

The Play Player's animation logic template activates a predefined player animation when the trigger condition is met.

To add the Play Player's Animation logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Play Player's Animation under the header "Effects".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="279">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Play On</td><td><p></p><p>Choose from the following options in the dropdown menu for when the Player animation should Start:</p><ol><li>On Game Start</li><li>On Player Touch</li><li>On Other Object Touch</li><li>On Click</li><li>On Broadcast: If selected, specify the broadcast to listen to.</li></ol></td></tr><tr><td>Broadcast</td><td>Enter a broadcast to be generated at the end of execution. This broadcast can be used as a trigger for other behaviors.</td></tr><tr><td>Animation</td><td>Select an animation for the player to execute from the dropdown list</td></tr><tr><td>Reset Automatically</td><td>Toggle button that specifies whether the player animation must reset</td></tr></tbody></table>

### Accessing the Play Player Animation Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [PlayPlayerAnimationTemplate](../../coding-using-t/t-logic-template-wrappers.md#playplayersanimationtemplate). You may also find the wrapper - [PlayerAnimationControlTemplate](../../coding-using-t/t-logic-template-wrappers.md#playeranimationcontroltemplate) useful
