---
icon: square-code
---

# Creating & Using Scripts

## About T\#

Terra Studio uses a programming language called T# (pronounced T-Sharp) - it has a syntax similar to C#. This was developed to provide developers who are used to writing code the flexibility to do almost anything on Terra's platforms.

A knowledge of Unity C# makes it super easy for you learn T#, but you need to take care of certain things that are different in T#. Read the section on Unsupported Functionalities in T# to know more.

## Creating your own Script

You can create your own T# scripts to customize game behavior. Here's how:

1. Click the Scripts Tab in the left panel.
2. To add a new script:
   1. Click the `+` icon.
   2. Enter a name and press Enter.&#x20;
3. Double-click the file to open it. Your script will compile and be ready.
4. The Visual Studio Code IDE will open all the scripts in the project.&#x20;
5. Locate your script in the Scripts Directory.&#x20;
6. You can now edit the default code to achieve your  desired behavior

## Adding your Script to an Asset

Scripts define how assets behave during gameplay. To enable this, attach a script to an asset. Here's how you can do it:

1. Select the asset to add the script.
2. Drag and drop the Script onto the asset.
3. Enable Advanced Mode. The Inspector Panel appears on the right.
4. You can change the script using the dropdown list containing all scripts in the project.

## Anatomy of a Script File

When you double-click a script in Terra Studio, it will be opened in a text editor. By default, Terra Studio will use VS Code Editor:

The initial contents of the script file will look something like this:

<pre class="language-csharp"><code class="lang-csharp">
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class MyFirstScript : TerraBehaviour
{
   //Use this for initialization
    private void Start()
    {
       
    }

    // Update is called once per frame
    private void Update()
    {
       
    }
}

<strong>
</strong></code></pre>

A script makes its connection with the internal workings of Unity by implementing a class which derives from the built-in class called `TerraBehaviour`. For multiplayer games, use `TerraNetBehaviour` instead, which provides network-specific functionality. You can think of a class as a kind of blueprint for creating a new script type that can be attached to GameObjects. Each time you attach a script component to a GameObject, it creates a new instance of the object defined by the blueprint. The name of the class is taken from the name you supplied when the file was created. The class name and file name must be the same to enable the script component to be attached to a GameObject.

The main things to note, however, are the two functions defined inside the class. The Update function is the place to put code that will handle the frame update for the GameObject. This might include movement, triggering actions and responding to user input, basically anything that needs to be handled over time during gameplay. To enable the Update function to do its work, it is often useful to be able to set up variables, read preferences and make connections with other GameObjects before any game action takes place. The Start function will be called by Terra Studio before gameplay begins (ie, before the Update function is called for the first time) and is an ideal place to do any initialization.

Unlike Unity, Terra Studio uses `TerraBehaviour` and not MonoBehavior:&#x20;

```csharp
public class MyFirstScript : TerraBehaviour
{
 // Enter functions here
}
// The following class does not work in Terra Studio because MonoBehavior is used
public class MyFirstScript : MonoBehaviour
{
 // Does not work since MonoBehavior is not supported
}
```

For multiplayer games, use `TerraNetBehaviour`:

```csharp
public class MyMultiplayerScript : TerraNetBehaviour
{
    // Enter functions here
    
    // Network-specific lifecycle methods
    public override void OnNetworkSpawn()
    {
        // Code to execute when the object spawns on the network
    }
    
    public override void OnNetworkDespawn()
    {
        // Code to execute when the object despawns from the network
    }
}
```

### `Start()`

This function gets called at the start of the game object's lifecycle and can be used to perform actions at the start of a game

```csharp
private void Start()
    {
      // Enter code to dictate what happens at the start of the game
       
    }
```

### `Update()`

This runs on every frame and can be used to dynamically update interactions

```csharp
private void Update()
    {
       // Enter code to tell what should happen on each frame
    }
```



## Adding Variables to an Asset

When you create a script in the Editor, Terra Studio automatically provides a template script for you to edit, which inherits from the `TerraBehaviour` class (or `TerraNetBehaviour` for multiplayer games). Inheriting from these classes means your script can behave like a type of component, and you can attach it to GameObjects like any other component.

When your script inherits from `TerraBehaviour` or `TerraNetBehaviour`, you can include properties and values in your script which you can then edit from the Editor Inspector, like you can with any other component.

Currently, in Terra Studio, you have to add local variables to the Asset GameObject in the editor interface only. To add a variable:

1. Add a script to the Asset GameObject
2. The Inspector Panel that appears on the right will show you both the script and the object variables tab.
3. Go to the Object Variables tab. There are four types of custom variables you can create:
   * String
   * Int
   * Float
   * GameObject
4. Click on the + icon next to the variable you want to add. Each variable needs to have a name and a value.

In Terra Studio, variables have local scope and can only be used in the scripts of the attached GameObject where they are defined.

Here is an example snippet code to use a variable declared in the editor:

```csharp
// The following script is attached to a GameObject where myName is added as an string Object Variable
// Let's say myName is set to 'Terra'
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class MainPlayer : TerraBehaviour 
{    
    private string myVar; // A string variable created to access the string variable created in the editor
    void Start () 
    {
        myVar = GetStringVariable("myName") // Accesses the string variable 'myName' created in the editor 
        Debug.Log("I am alive and my name is " + myVar);
        // The console will output "I am alive and my name is Terra"
        // Note that if myName is not added to the GameObject in the editor, this will throw up an error
    }
}
```



## Accessing Variables in your script

Variables created in an asset can be referenced in all scripts that are added to that asset. Here is how you access the variables:&#x20;

First, declare new variables of the same type to access those created in the editor:

```csharp
private float myVariable1; 
```

You can access these variables inside any function:

```csharp
 private void Start()
    {
       myVariable1 = GetFloatVariable("a"); // Access the float variable 'a' created in the editor
       // Add code here
    }
```

You can do this for all variable types: &#x20;

```csharp
public class MyFirstScript : TerraBehaviour
{
   //Declare new variables to access the variables you have created
   private float myVariable1; // To access the float variable
   private string myVariable2; // To access the String Variable
   private int myVariable3; // To access the int variable
   private GameObject myVariable4; // To access the game object variable
    
    private void Start()
    {
       myVariable1 = GetFloatVariable("a"); // Access the float variable 'a' created in the editor
       myVariable2 = GetStringVariable("b"); // Access the string variable 'b'  
       myVariable3 = GetIntVariable("c"); // Access the integer variable 'c'
       myVariable4 = GetGameObjectVariable("d"); // Access the game object variable 'd'
       // Add code here 
    }

    private void Update()
    {
       // Add code here
    }
}
```



## Event Functions

A script in Terra Studio is not like the traditional idea of a program where the code runs continuously in a loop until it completes its task. Instead, Terra Studio passes control to a script intermittently by calling certain functions that are declared within it. Once a function has finished executing, control is passed back to Terra Studio. These functions are known as event functions since they are activated by Terra Studio in response to events that occur during gameplay.&#x20;

Terra Studio uses a naming scheme to identify which function to call for a particular event. For example, you will already have seen the Update function (called before a frame update occurs) and the Start function (called just before the object’s first frame update). The following are some of the most common and important events:

### Regular Update Events

A game is rather like an animation where the animation frames are generated on the fly. A key concept in games programming is that of making changes to position, state and behavior of objects in the game just before each frame is rendered. The `Update` function is the main place for this kind of code in Terra Studio. Update is called before the frame is rendered and also before animations are calculated.

```csharp
void Update() {
    float distance = speed * Time.deltaTime * Input.GetAxis("Horizontal");
    transform.Translate(Vector3.right * distance);
}
```

The **physics engine** also updates in discrete time steps in a similar way to the frame rendering. A separate event function called `FixedUpdate` is called just before each physics update. Since the physics updates and frame updates do not occur with the same frequency, you will get more accurate results from physics code if you place it in the FixedUpdate function rather than Update.

```csharp
void FixedUpdate() {
    Vector3 force = transform.forward * driveForce * Input.GetAxis("Vertical");
    rigidbody.AddForce(force);
}

```

It is also useful sometimes to be able to make additional changes at a point after the Update and FixedUpdate functions have been called for all objects in the **scene** and after all animations have been calculated. An example is where a **camera** should remain trained on a target object; the adjustment to the camera’s orientation must be made after the target object has moved. Another example is where the script code should override the effect of an animation (say, to make the character’s head look towards a target object in the scene). The `LateUpdate` function can be used for these kinds of situations.

```csharp
void LateUpdate() {
    Camera.main.transform.LookAt(target.transform);
}
```

\


## Coroutines

A coroutine allows you to spread tasks across several frames. In Terra Studio, a coroutine is a method that can pause execution and return control to Terra Studio but then continue where it left off on the following frame.

In most situations, when you call a method, it runs to completion and then returns control to the calling method, plus any optional return values. This means that any action that takes place within a method must happen within a single frame update.

In situations where you would like to use a method call to contain a procedural animation or a sequence of events over time, you can use a coroutine.

However, it’s important to remember that coroutines aren’t threads. Synchronous operations that run within a coroutine still execute on the main thread. If you want to reduce the amount of CPU time spent on the main thread, it’s just as important to avoid blocking operations in coroutines as in any other script code.&#x20;

It’s best to use coroutines if you need to deal with long asynchronous operations.&#x20;

### Coroutine example

As an example, consider the task of gradually reducing an object’s alpha (opacity) value until it becomes invisible:

```csharp
void Fade()
{
    Color c = renderer.material.color;
    for (float alpha = 1f; alpha >= 0; alpha -= 0.1f)
    {
        c.a = alpha;
        renderer.material.color = c;
    }
}
```

In this example, the Fade method doesn’t have the effect you might expect. To make the fading visible, you must reduce the alpha of the fade over a sequence of frames to display the intermediate values that Terra Studio renders. However, this example method executes in its entirety within a single frame update. The intermediate values are never displayed, and the object disappears instantly.

To work around this situation, you could add code to the `Update` function that executes the fade on a frame-by-frame basis. However, it can be more convenient to use a coroutine for this kind of task.

In T#, you declare a coroutine like this:

```csharp
IEnumerator Fade()
{
    Color c = renderer.material.color;
    for (float alpha = 1f; alpha >= 0; alpha -= 0.1f)
    {
        c.a = alpha;
        renderer.material.color = c;
        yield return null;
    }
}
```

A coroutine is a method that you declare with an [IEnumerator](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator) return type and with a [yield](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/yield) return statement included somewhere in the body. The `yield return null`line is the point where execution pauses and resumes in the following frame. To set a coroutine running, you need to use the [StartCoroutine](https://docs.unity3d.com/2021.3/Documentation/ScriptReference/MonoBehaviour.StartCoroutine.html) function:

```csharp
void Update()
{
    if (Input.GetKeyDown("f"))
    {
        StartCoroutine(Fade());
    }
}
```

The loop counter in the Fade function maintains its correct value over the lifetime of the coroutine, and any variable or parameter is preserved between `yield` statements.

### Coroutine time delay

By default, Terra Studio resumes a coroutine on the frame after a `yield` statement. If you want to introduce a time delay, use [WaitForSeconds](https://docs.unity3d.com/2021.3/Documentation/ScriptReference/WaitForSeconds.html):

```csharp
IEnumerator Fade()
{
    Color c = renderer.material.color;
    for (float alpha = 1f; alpha >= 0; alpha -= 0.1f)
    {
        c.a = alpha;
        renderer.material.color = c;
        yield return new WaitForSeconds(.1f);
    }
}
```

You can use `WaitForSeconds` to spread an effect over a period of time, and you can use it as an alternative to including the tasks in the `Update` method. Terra Studio calls the `Update` method several times per second, so if you don’t need a task to be repeated quite so often, you can put it in a coroutine to get a regular update but not every single frame.

For example, you might have an alarm in your application that warns the player if an enemy is nearby with the following code:

```csharp
bool ProximityCheck()
{
    for (int i = 0; i < enemies.Length; i++)
    {
        if (Vector3.Distance(transform.position, enemies[i].transform.position) < dangerDistance) {
                return true;
        }
    }

    return false;
}
```

If there are a lot of enemies then calling this function every frame might introduce a significant overhead. However, you could use a coroutine to call it every tenth of a second:

```csharp
IEnumerator DoCheck()
{
    for(;;)
    {
        if (ProximityCheck())
        {
            // Perform some action here
        }
        yield return new WaitForSeconds(.1f);
    }
}
```

This reduces the number of checks that Terra Studio carries out without any noticeable effect on gameplay.

## Handling MouseClick

The code below sends a debug message when a user clicks on the object to which this script is attached.

```csharp

public class ClickHandler : TerraBehaviour
{
    // This method is called when the user clicks on the GameObject
    private void OnMouseDown()
    {
        // Initiate an action, e.g., print a message to the console
        Debug.Log("GameObject clicked!");
        // You can add a function to do something on click as well - like the dummy function below
        // Feel free to replace it with something functional
        doSomething();
       
    }
}
```

## Handling Collision

The code below sends a debug message when the gameObject to which the script is attached collides with another game object - a cube (whose name is declared in the object variable for the current game object as "`cube`")

```csharp
public class CollisionHandler : TerraBehaviour
{
    // Reference to the specific GameObject you want to check for collision
    private GameObject targetObject;
    
    // Accessing the game object variable on Game start
    private void Start()
    {
    // Assuning that the variable name for the target object was set as 'cube' on the editor    
       targetObject = GetGameObjectVariable("cube");     
   }


    // This method is called when the collider attached to this GameObject
    // collides with another collider.
    private void OnCollisionEnter(Collision collision)
    {
        // Check if the collision was with the specific GameObject
        if (collision.gameObject == targetObject)
        {
            // Initiate an action, e.g., print a message to the console
            Debug.Log("Collided with the specific GameObject!");

            // Enter code below to complete some other action on collision as well
        }
    }
}

```

## Multiplayer-Specific Events

For multiplayer games using `TerraNetBehaviour`, there are special network lifecycle methods:

```csharp
csharpCopypublic override void OnNetworkSpawn()
{
    // Code to execute when the object spawns on the network
    // This is a good place to initialize network variables
}

public override void OnNetworkDespawn()
{
    // Code to execute when the object despawns from the network
    // Clean up any network-specific resources here
}
```

### Listening to Broadcasts

To listen to broadcasts in the new Terra Studio variant, you need to implement a custom solution for broadcast handling, as the `OnBroadcasted` method that was available in the StudioBehaviour class is no longer available.&#x20;
