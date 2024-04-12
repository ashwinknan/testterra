# Collide

Any Object with the Collide template attached to it sends a broadcast either when <mark style="color:purple;">you collide with it</mark> or when a <mark style="color:purple;">different object touches it</mark>.

| Parameters  | Type                                                                                                                                                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Event | game start, player touches, other object touches, mouse clicked, broadcast listened                                                                                                                                                         |
| Effects     | Change in Player or Asset properties, Change in Game Scene Environment, Change in Game Systems, Change in an Asset's Orientation, Create or Elimination existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                                                                                                                                                 |

To add the Update Score behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Update Score behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Update Score.**

You can customize the below-mentioned parameters according to your requirements:

You can customize these parameters:

<table><thead><tr><th width="259">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Start On</td><td>Choose how to collide. You have <code>OnPlayerCollide</code> or <code>OtherObjectTouches</code></td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when you collide with the object.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when you collide with the object.</td></tr><tr><td>BroadcastData</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br><code>The broadcast is sent when you collide with the object.</code></td></tr></tbody></table>
