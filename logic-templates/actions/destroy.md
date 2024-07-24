# Destroy

The Destroy logic template is used when you want to remove or destroy assets from the game scene on a certain trigger. The asset with this logic template are destroyed without any trace of them being there.

This logic template is very similar to the Collectable behaviour, the only difference being that the Collectable contributes to a score group and this does not. In both logic templates, the asset disappears after the trigger.

To add the Destroy logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Destroy under the header "Action".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:

<table><thead><tr><th width="288">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Destroy When</td><td><p>You can choose the trigger when to destroy the asset.<br>- When the game starts</p><p>- When a different asset touches the asset having the behaviour<br>- After a broadcast message has been received by the asset. <br>- When the player touches the asset.<br>- When the object is clicked.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the asset is destroyed.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the asset is destroyed.</td></tr><tr><td>Broadcast Data</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the asset is destroyed.</td></tr><tr><td>Destroy After</td><td>The time in seconds after which the asset disappears from the scene.</td></tr></tbody></table>

### Accessing the Destroy Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [DestroyTemplate](../../coding-using-t/t-logic-template-wrappers.md#destroytemplate)
