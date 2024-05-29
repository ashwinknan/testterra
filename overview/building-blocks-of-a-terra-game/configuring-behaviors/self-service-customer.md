# Self-service customer

Self-service customers are a distinctive behavior type frequently employed in Tycoon Games. They allow creators to simulate customer actions using NPC assets, particularly in self-service stores. For instance, applying the Self-service customer behavior to a "bunny" visiting a store to purchase 5 apples, 6 eggs, and 2 bananas would prompt the NPC to enter the store, locate the respective shelves, collect the desired items, proceed to the checkout counter for billing, and finally, complete the transaction to obtain the items.

To add the Self-service customers behavior to an asset, follow these steps:

1. Select the asset you wish to apply the Self-service customers behavior to.
2. In the Inspector panel, click on **Add Behavior**.
3. From the list of behaviors, choose **Self-service customers.**

You can customize the below-mentioned parameters according to your requirements:

| Parameter                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Self service customer when | <p></p><p>This is a dropdown from where you need select any one of the following Start Events for this behaviour initiate: <br> <br>1.. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>2. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>3. When the player touches the currently selected Asset: Select "Player Touchers"<br>4. When the Asset is clicked: Select "On Click"</p> |
| Sound Effect on Start      | Choose a short chime to play on behaviour execution                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Visual Effect on Start     | Choose a small visual effect to play n behaviour execution                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Broadcast On Collection    | <p>Choose to enter a broadcast that can be used as a trigger for any other behaviour.<br>The broadcast is sent when the item is collected</p>                                                                                                                                                                                                                                                                                                                                                                      |