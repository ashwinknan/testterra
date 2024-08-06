# Reset Score

There are two distinct ways of resetting a player's score in Terra Creator Studio:

### Resetting the Player Score through Logic Templates

To reset the player score using logic templates, you need to add the Reset Score logic template using these steps:

1. Go to the Logic Tab.
2. Select Reset Score under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="202">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Update When</td><td>Allows you to define the trigger for resetting the score. There are four triggers allowed:<br>Player Touches- Resets the score when the player touches the selected object<br>Other Object Touches - Resets the score when another object touches the selected object<br>Clicked - Resets the score when you click the selected object<br>Broadcast Listened - Resets the score when it listens to a broadcast from another object</td></tr><tr><td>Score Group</td><td>Define which score group needs to be reset based on the trigger event happening</td></tr><tr><td>Broadcast</td><td>Define any broadcast for another object to listen to</td></tr></tbody></table>

### Resetting the Player Score through T\#

You can choose not to use any logic template and directly use the T# wrapper for resetting score - the  [ResetScoreTemplate](../../coding-using-t/t-logic-template-wrappers.md#resetscoretemplate)
