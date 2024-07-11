# T# Basics

## About T\#

T# is a scripting language developed by Terra - which has a syntax similar to C#. This was developed to provide developers who are used to writing code the flexibility to do almost anything on Terra's platforms. In Terra Studio 3.0, creators ability to make a variety of games was limited by the number of behavior blocks that were available in its library

T# removes this constraint. Now even if you don't have a behavior block in Terra Studio, you can go ahead and write your own script to make that happen.

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

1. Select the asset to add the script
2. Go to the Logic Tab on the left
3. Drag and drop the Studio Machine Behavior onto the asset.
4. Enable Advanced Mode. The Inspector Panel appears on the right.
5. Go to the Studio Machine Tab in the Inspector Panel and open the dropdown to see all scripts in the project.&#x20;
6. Choose the script you want to add.

## Basic Structure of a default T# Script

When you open a script in Visual Studio Code, a default script like this appears:

```csharp

using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class MyFirstScript : StudioBehaviour
{
    private void Start()
    {
       
    }

    private void Update()
    {
       
    }

    public override void OnBroadcasted(string x)
    {
        
    }
}

```

### `Start()`

This function gets called at the start of the game object's lifecycle and can be used to perform actions at the start of a game

```csharp
private void Start()
    {
       
    }
```



### `Update()`

This runs on every frame and can be used to&#x20;

```csharp
private void Update()
    {
       
    }
```



### `OnBroadcasted()`

This runs whenever a broadcasted signal is listened to by the object

```csharp
public override void OnBroadcasted(string x)
    {
    // The code below executes doSomething when it listens to the broadcast x
        if(String.Equals(x,"signal")){
        doSomething();
        }
        
    }
```

## Adding Custom Variables to an Asset

Add custom local variables to an asset to use them in your scripts. To add a variable,

1. Select the asset to add the script
2. Go to the Logic Tab on the left
3. Drag and drop the Studio Machine Behavior onto the asset.
4. Enable Advanced Mode. The Inspector Panel appears on the right.
5. Go to the Object Variables tab. There are four types of custom variables you can create:
   1. String
   2. Int
   3. Float
   4. GameObject
6. Click on the + icon next to the variable you want to add. Each variable needs to have a name and a value.

## Accessing Variables in your script

Variables created in an asset can be referenced in all scripts that are added to that asset. Here is how you access the variables:&#x20;

First, declare new variables of the same type to access those created in the editor:

```csharp
private float myVariable1; // A float variable created to access the float variable created in the editor
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
public class MyFirstScript : StudioBehaviour
{
 
 //Declare new variables to acceess the variables you have created
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

    public override void OnBroadcasted(string x)
    {
      // Add code here         
    }
}
```



## Generating a Custom Broadcast

You can create your own custom broadcast inside any function

```csharp


public class MyFirstScript : StudioBehaviour
{
    private void Start()
    {
         OnBroadcast("signal"); // Generates the broadcast "signal"       
    }

    private void Update()
    {
       // Add code
    }

    public override void OnBroadcasted(string x)
    {
       // Add code        
    }
}me code
```

## Listening to a Custom Broadcast

You can listen to a created broadcast using the OnBroadcasted() function

```csharp
// Some code
```

## Accessing Behavior Templates

Terra has a list of behavior templates which you can use to modify. You can write your own behaviors from scratch through Behavior Template Wrappers. &#x20;

First, access all the wrappers of a specific behavior template by declaring a variable like this:

```csharp
CollectableTemplate collect = (GetTemplate(typeof(CollectableTemplate) as CollectableTemplate);
//the variable 'collect' can now be used to access all the properties of the collect behavior
```

Now use this variable to change all the properties of that behavior:

```csharp
CollectableTemplate collect = (GetTemplate(typeof(CollectableTemplate) as CollectableTemplate);
collect.Score = 10; // Score is a property which can now be modified 
```

A list of accessible variables for each template can be found here are written in the next page

{% hint style="info" %}
Currently, behavior templating doesn't work with objects instantiated using T#.
{% endhint %}
