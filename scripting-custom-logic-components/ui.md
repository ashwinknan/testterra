# Adding UI using T\#

To add game UI using T#, you need to do the following

1. From the main toolbar, pick the primitives dropdown. Select `Edit UI`
2. You will see a UI Picker in the Inspector Panel. From the UI picker,  choose the UI you want
3. Edit in portrait/ landscape as you wish.

Terra studio will automatically handle the spawning of the UI in landscape / portrait depending on the device specs. The UI instantiated in play-mode will be separate from the one in the editor, but maintains the same hierarchy and edits you make.To access the instantiated UI, these are the steps:

1. Add the Studio Machine Logic Component to “EditCanvas\_1" parent in Layers
2. Add the following code Snippet that logs “Hello” when a button in the UI is clicked.  Customize as required

```csharp
// This script will add a button UI to the game which when clicked will log the message Hello on the Debug panel
public class TestScript : StudioBehaviour
{
    private void Start()
    {
        var UI = GetTemplate(typeof(EditUITemplate)) as EditUITemplate;
        var instantiatedUI = UI.GetInstantiatedUI;
        var buttonObj = StudioExtensions.FindDeepChild(instantiatedUI.transform, "[BUTTONNAMEHERE]");
        var buttonComponent = buttonObj.GetComponent(typeof(Button)) as Button;
        buttonComponent.onClick.AddListener(()=>{Debug.LogError("Hello");}); // Can be modified to perform the action you want
    }
    private void Update()
    {
    }
    public override void OnBroadcasted(string x)
    {
}
```

