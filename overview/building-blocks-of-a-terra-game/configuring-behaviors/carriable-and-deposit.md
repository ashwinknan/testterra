# Carriable and Deposit

A carriable is a behavior that, when attached to a game asset, enables the player to carry it. A deposit is a behavior that, when applied to an asset, allows it to collect a specified carriable. This can lead to a score increase or trigger a broadcast as a consequence

#### Carriable:

| Parameters  | Type                                                                                                                   |
| ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| Start Event | player touches, mouse clicked, Timer, magnetic range, broadcast listen, other object touches                           |
| Effects     | Change in Game Systems, Eliminates existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | Independent                                                                                                            |

#### Deposit:

| Parameters  | Type                                                                                                                   |
| ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| Start Event | player touches, mouse clicked, On Trigger Stay,  broadcast listened, other object touches                              |
| Effects     | Change in Game Systems, Eliminates existing Game Scene Objects, Generate a Broadcast Signal, Enable an SFX or Particle |
| Type        | dependent                                                                                                              |

To add the Carriable behavior to an asset, follow these steps:

{% embed url="https://www.loom.com/share/f67cf9873a584bebae54cf5c94e1ffda?sid=f7158aca-4596-4c1d-b54d-f1bd5877fddb" %}
Carriable and deposit
{% endembed %}

1. Select the asset you wish to apply the Carriable behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose Carriable.

You can customize the below-mentioned parameters according to your requirements:

| Parameter          | Description                                                                                                                                                                                                                             |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Group              |                                                                                                                                                                                                                                         |
| Carry on           | <p></p><p>Choose when the item is “carried”, using the dropdown:</p><ul><li>when player touches</li><li>when clicked on screen</li><li>when in a magnet range</li><li>When the player has to stay near it for a specific time</li></ul> |
| Play SFX           | Choose a short chime to play when item is collected                                                                                                                                                                                     |
| Play VFX           | Choose a small visual effect to play when item is collected                                                                                                                                                                             |
| Play SFX           |                                                                                                                                                                                                                                         |
| Play VFX           |                                                                                                                                                                                                                                         |
| Play SFX           |                                                                                                                                                                                                                                         |
| Play VFX           |                                                                                                                                                                                                                                         |
| Size of carriable  |                                                                                                                                                                                                                                         |
| Score Group        | The point of the Collectable will be contributed to the score group. You can either add it to Main Score group or make your own custom group                                                                                            |
| Lerp               |                                                                                                                                                                                                                                         |
| Lerp Time          |                                                                                                                                                                                                                                         |
| Score              | Enter a numerical score value to update when collected.                                                                                                                                                                                 |
| IsMultiLevel       | Enabling this parameter can upgrade to a higher value on level up                                                                                                                                                                       |
| Broadcast          | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                           |

Configure the player setting for the carriable behaviour:

1. Navigate to the essentials tab from the builder menu.
2. Select the PlayerControllerDrawer from the builder panel. this would open the inspector panel
3. Navigate to carriable properties section in the inspector pannel.

| Parameter             | Description                                                                  |
| --------------------- | ---------------------------------------------------------------------------- |
| Locator for cariable  | set the position of the carriable on the player using the record button      |
| Limit                 | the number of carriable can be limited using this field                      |
| Stack offset          | Using this option you can set the position of the carrible around the player |

To add the Deposit behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Carriable behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose Carriable.

You can customize the below-mentioned parameters according to your requirements:
