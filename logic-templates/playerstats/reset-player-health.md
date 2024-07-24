# Reset Player Health

When a player interacts with an object tagged with the Reset Player Health logic template, the player's health is fully restored. This can be useful when a player respawns after dying, enters a safe zone, collects healing items, or faces similar situations.

To add the Reset Player Health logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Reset Player Health under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour.<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When the object is clicked.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health is reset</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health is reset</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when health is restored.</td></tr></tbody></table>

### Accessing the Reset Player Health Logic Template using T\#

There are currently no available T# Wrappers for this template.&#x20;
