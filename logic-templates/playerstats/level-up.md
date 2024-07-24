# Level Up

Level up behaviour is used to upgrade different in-game assets based on the the upgrade paths of objects defined using the [Level Mapper](../../conceptual-guides/setting-up-game-systems.md) game system.

To add the Level Mapper logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Level Mapper under the header "PlayerStats".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor:

<table><thead><tr><th width="239">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Level up when</td><td>You can choose the trigger to activate the behaviour <br>- After a broadcast message has been received by the object<br>- When the player touches the object<br>- When a different object touches the object<br>- When you click on the object</td></tr><tr><td>Sound Effect on Start</td><td>Choose a sound effect to play on execution</td></tr><tr><td>Visual Effect on Start</td><td>Choose a visual effect to play on execution</td></tr><tr><td>Manager group</td><td>Helps to choose the score group based on which the Level up will be decided</td></tr><tr><td>Broadcast Success</td><td>Define a broadcast to be generated when the level up is successful</td></tr><tr><td>Broadcast Fails </td><td>Define the broadcast to be generated when the level up fails</td></tr><tr><td>Execute Times</td><td>Number of times behaviour need to be excuted </td></tr></tbody></table>

### Accessing the Level Up Logic Template using T\#

There are currently no available T# Wrappers for this template.&#x20;
