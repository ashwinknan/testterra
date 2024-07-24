# Load Scene

The Load Scene logic template enables you to transition from one game environment (scene)  to another, such as progressing from one level to the next or exploring a new area.&#x20;

To add the Load Scene logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Load Scene under the header "Game".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Load Scene When</td><td><p></p><p>Choose from this dropdown when to transition to a different scene:</p><ul><li><strong>Broadcast Listened</strong>: After the object receives a broadcast message.</li><li><strong>Player Touch</strong>: When the player touches the object.</li><li><strong>Other Object Touch</strong>: When another object touches the object.</li><li><strong>Clicked</strong>: When you click on the object.</li></ul></td></tr><tr><td>Scenes to Load</td><td>Click the + button to choose the next scene to load when the trigger condition is met. It displays a list of all available scenes in the game.</td></tr><tr><td>Can Repeat Previous Level</td><td>Toggle that specifies whether the player can repeat the previous level</td></tr></tbody></table>

## Accessing the Load Scene Template using T\#

Currently, there's no T# Wrapper available to customize this logic template beyond the scene editor's capabilities. However, you can write your own code in T# to implement this logic from scratch.
