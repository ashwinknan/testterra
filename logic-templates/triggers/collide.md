# Collide

Any object with the Collide logic template attached sends a broadcast either when you collide with it or when a different object touches it.

To add the Collide logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Collide under the header "Triggers".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor l:

<table><thead><tr><th width="259">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start On</td><td>Choose how to collide. You have OnPlayerCollide or OtherObjectTouches</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when you collide with the object.</td></tr><tr><td>BroadcastData</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when you collide with the object.</td></tr></tbody></table>
