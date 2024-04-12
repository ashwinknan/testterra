# Increase Player Health

When triggered, the Increase Player Health behavior boosts the player's health. The behavior can be activated in response to various events, such as the player collecting coins or other items that improve health.&#x20;

| Parameters  | Type                                                                                 |
| ----------- | ------------------------------------------------------------------------------------ |
| Start Event | player touches, broadcast listened                                                   |
| Effects     | Change in Player properties,  Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                          |

To add the Increase player health behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Increase player health behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Increase player health.**

You can customize the below-mentioned parameters according to your requirements:

<table><thead><tr><th width="276">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>When</td><td>You can choose the trigger to activate the behaviour<br>- After a broadcast message has been received by the object<br>- When the player touches the object</td></tr><tr><td>By Point</td><td>The player's health will increase by the defined amount when the behaviour is triggered.</td></tr><tr><td>Play SFX</td><td>Choose a sound effect to play when the health increases.</td></tr><tr><td>Play VFX</td><td>Choose a visual effect to play when the health increases.</td></tr><tr><td>Broadcast</td><td>Choose to enter a broadcast that can be used as a trigger for any other behavior. <br>The broadcast is sent everytime the player health increases.</td></tr></tbody></table>
