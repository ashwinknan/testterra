# Stop Player movement

When a player comes into contact with an asset that has the StopPlayerMovement logic template applied, the player's motion in the game environment is halted. This logic template locks the player in their current position and deactivates any movement through the controller.

To add the Stop Player Movement logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Stop Player Movement under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="246">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start When</td><td><p>You can choose the trigger to activate the behaviour </p><p>- When the game starts<br>- After a broadcast message has been received by the object.<br>- When the player touches the object.<br>- When a different object touches the object.<br>- When you click on the object.</p></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the player stops moving.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the player stops moving.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when the player stops moving again.</td></tr></tbody></table>



### Accessing the Stop Player Movement Logic Template using T\#

There are currently no available T# Wrappers for this template.&#x20;
