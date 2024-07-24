# Attach Object

The Attach Object Logic Template allows you to attach one object to another, making the new object a child of the original object.

To add the Attach Object logic template, follow these steps:

1. Go to the Logic Tab.
2. Select Attach Object under the header "Mechanics".
3. Drag and drop it onto the desired asset.

You can customize the below-mentioned parameters according to your requirements:

| Parameter                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">`AttachOn`</mark>     | <p>This is a dropdown from where you need select any one of the following Start Events for the template<br> <br>1. When the behavior  when the game starts: Select "Game Start"<br>2. When any other Asset touches the currently selected Asset: Select "Other Object Touch"<br>3. When a particular broadcast is generated in the game: Select "Broadcast Listened" and specify the name of the signal to listen to<br>4. When the player touches the currently selected Asset: Select "Player Touchers"<br>5. When the Asset is clicked: Select "On Click" </p> |
| <mark style="color:blue;">`Attach_To`</mark>    | Select from the dropdown whether you want to attach the object to the Player or A Game Object.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| <mark style="color:blue;">`Attach To`</mark>    | <p>If you chose GameObject, drag and drop the game object references from the layers here.<br><br>This will be set to None if you selected Player on Attach_To</p>                                                                                                                                                                                                                                                                                                                                                                                                |
| <mark style="color:blue;">`KeepWorldPos`</mark> | Toggle to indicate if you want to keep the world position of the object                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <mark style="color:blue;">`Offset`</mark>       | Indicate the offset between the parent and the child                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

### Accessing Attach Object using T\#

There is currently no T# Wrapper to directly access this logic template.&#x20;

