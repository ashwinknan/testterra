# Debris

The Debris behavior plays a crucial role in shaping the post-destruction landscape within the game environment, alongside the Debris Destructible behavior. It allows us to specify which asset will be utilized as \`debris after destruction

| Parameters  | Type                                                                   |
| ----------- | ---------------------------------------------------------------------- |
| Trigger     | Event based trigger (Broadcast listen)                                 |
| Outcome     | Visual or auditory effects (like - SFX,VFX),  Trigger another behavior |
| Type        | Dependent                                                              |

One or multiple triggers can be created, resulting in one or multiple outcomes.

To add the Switch behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Debris behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Debris.**

You can customize the below-mentioned parameters according to your requirements:

| Parameter | Description                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------- |
| Group     | This creates a group for the object that will help you to connect the debris to Debris Destructible behavior. |
