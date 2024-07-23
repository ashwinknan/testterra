# Collide

Any object with the Collide behavior attached sends a broadcast either when you collide with it or when a different object touches it.

| Parameters  | Type                                                   |
| ----------- | ------------------------------------------------------ |
| Start Event | player touches, other object touches                   |
| Effects     | Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                            |

To add the Collide behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Collide behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Collide.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="259">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start On</td><td>Choose how to collide. You have OnPlayerCollide or OtherObjectTouches</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when you collide with the object.</td></tr><tr><td>BroadcastData</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent when you collide with the object.</td></tr></tbody></table>
