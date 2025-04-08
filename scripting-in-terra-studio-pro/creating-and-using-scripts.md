---
icon: square-code
---

# Creating & Using Scripts

## 🚀 About T\#

**T# (pronounced T-Sharp)** is Terra Studio’s scripting language, designed to feel familiar to Unity developers with a syntax similar to C#. It gives creators the **freedom to write custom logic** for their games .

If you already know Unity C#, you’ll feel right at home. However, **T# has a few important differences** to support live editing and interpreted execution.\
👉 Be sure to check out the [Key Differences - T# versus C# ](key-differences-t-versus-c/)section to avoid surprises.

## 🛠️ Creating & Using Scripts in Terra Studio

### ✨ Step 1: Add the TerraMachine Component

In the latest Terra Studio workflow, **scripts are attached to GameObjects through the `TerraMachine` component**.

To set this up:

1. Select your GameObject in the scene.
2. In the right-hand Inspector panel, click **"Add Component"**.
3. Search for and add the **`TerraMachine`** component.
4. In the dropdown, select the T# script you want this machine to run.

> 💡 You must create the script before assigning it in the TerraMachine (see below).

### ✨ Step 2: Create a T# Script

1. Open the **Scripts** tab in the left panel.
2. Click the ➕ button to create a new script.
3. Name the script and press Enter.
4. Your script will open in **Visual Studio Code**, along with all other project scripts.
5. You’ll find your file in the **Scripts Directory**.

Now, edit the generated class to implement your desired game behavior.

## 📦 Anatomy of a Script

Here’s what a default T# script looks like:

```csharp
using System;
using System.Collections;
using Terra.Studio;
using Terra.Studio.Exposed;
using Terra.Studio.Exposed.Layers;
using UnityEngine;

public class MyFirstScript : TerraBehaviour
{
    private void Start()
    {
        // Initialization logic
    }

    private void Update()
    {
        // Frame-based logic
    }
}
```

#### 🧬 Key Concepts:

* **All scripts must extend `TerraBehaviour` or `TerraNetBehaviour`** (for multiplayer).
* The class name **must match the file name**.
* `Start()` runs once at the beginning.
* `Update()` runs on every frame.

***

## 👾 Multiplayer Scripting

For networked games, extend `TerraNetBehaviour` instead:

```csharp
public class MyMultiplayerScript : TerraNetBehaviour
{
    public override void OnNetworkSpawn()
    {
        // Initialization when object spawns on network
    }

    public override void OnNetworkDespawn()
    {
        // Clean-up when object despawns
    }
}
```

These methods are called automatically during multiplayer object lifecycles.

## 🪄 Setting Up Variables in the Unity Editor

To define variables for your script:

1. **Select a GameObject** in your Unity scene.
2. In the Inspector, **add a TerraMachine component**.
3. Select the T# script you want this object to run.
4. Once selected, a new section called **Object Variables** will appear below the script field.
5. Click the **+ icon** to add a new variable.
6. You can create one of four types:
   * **String**
   * **Float**
   * **Int**
   * **GameObject**
7. Each variable must have:
   * A unique **name**
   * An **initial value** that the script can read when the game starts

{% hint style="warning" %}
These variables can only be accessed from the script attached to the same TerraMachine. They are not shared globally or across multiple objects unless explicitly managed.
{% endhint %}

## 🧪 Accessing Variables in T# Scripts

To use these variables in your script, you must:

1. Declare local variables inside your script to store their values.
2. Use Terra’s built-in **getter methods** like `GetFloatVariable()` or `GetStringVariable()` inside a function like `Start()` to retrieve them.

**✅ Example: Accessing a string variable**

Let's say you've added a string variable named `myName` to a GameObject’s TerraMachine and set it to `"Terra"`.

```csharp
using System;
using System.Collections;
using Terra.Studio;
using UnityEngine;

public class MainPlayer : TerraBehaviour 
{    
    private string myVar; // Local variable to store the editor-defined value

    void Start() 
    {
        myVar = GetStringVariable("myName");
        Debug.Log("I am alive and my name is " + myVar);
        // Output: "I am alive and my name is Terra"
    }
}
```

{% hint style="danger" %}
If the variable `"myName"` does not exist on this object, your code will throw an error at runtime. You will also get an error if&#x20;
{% endhint %}

#### 🧩 Example: Accessing Multiple Types of variables

You can also fetch multiple variables of different types in one script:

```csharp
public class MyFirstScript : TerraBehaviour
{
    // Declare variables to store values fetched from Object Variables
    private float myFloat;
    private string myString;
    private int myInt;
    private GameObject myGameObject;

    private void Start()
    {
        myFloat = GetFloatVariable("speed");
        myString = GetStringVariable("label");
        myInt = GetIntVariable("score");
        myGameObject = GetGameObjectVariable("target");

        // You can now use these variables in Update or other methods
    }

    private void Update()
    {
        // Example usage
        transform.Translate(Vector3.forward * myFloat * Time.deltaTime);
    }
}
```

{% hint style="warning" %}
Note that all variables values are assigned in the Start() method
{% endhint %}

## ⚙️ Event Functions in Terra Studio

In Terra Studio, you don’t write continuous loops like in traditional programming. Instead, the engine calls **event functions** in response to gameplay events — such as object initialization, collisions, updates per frame, user clicks, and more.

If you’ve worked with Unity before, this will feel very familiar. However, keep in mind that you are writing T# scripts that run inside the **TerraMachine** component added to GameObjects in your Unity scene.

T# supports a **subset of Unity-style lifecycle methods**, along with some limitations. This section outlines which events are supported and how to use them effectively.

***

### ▶️ Game Lifecycle Events

#### **`Start()`**

The `Start` method runs **once at the beginning of a GameObject’s lifecycle** — just after all variables and components have been initialized. This is where you should fetch object variables, set up references, or run any custom initialization logic.

```csharp
csharpCopyEditprivate void Start()
{
    Debug.Log("GameObject has started!");
}
```

#### **`Update()`**

The `Update` method is called **once per frame**. Use this for dynamic logic such as input handling, movement, or timers.

```csharp
csharpCopyEditprivate void Update()
{
    float distance = speed * Time.deltaTime * Input.GetAxis("Horizontal");
    transform.Translate(Vector3.right * distance);
}
```

***

### 🛞 Physics Events

## **`FixedUpdate()`**

This is used for physics-based updates. It runs at a fixed interval and is ideal for applying forces or detecting rigidbody behavior.

```csharp
private void FixedUpdate()
{
    Vector3 force = transform.forward * driveForce * Input.GetAxis("Vertical");
    rigidbody.AddForce(force);
}
```

{% hint style="danger" %}
&#x20;**Note:** `LateUpdate()` is **not supported** in T#. To execute logic _after_ rendering or animations, use a **coroutine with `WaitForEndOfFrame()`**.
{% endhint %}

***

### ⏳ Coroutines

T# supports Unity-style **coroutines** using `IEnumerator`. These let you pause and resume logic across multiple frames — useful for animations, time-based triggers, or conditional delays.

Here’s a basic coroutine:

```csharp
IEnumerator Fade()
{
    Color c = renderer.material.color;
    for (float alpha = 1f; alpha >= 0; alpha -= 0.1f)
    {
        c.a = alpha;
        renderer.material.color = c;
        yield return new WaitForSeconds(0.1f); // Waits before next iteration
    }
}
```

You start a coroutine using:

```csharp
StartCoroutine(Fade());
```

***

#### ⏱ Coroutine Timing Example

Let’s say you want to check if an enemy is nearby, but only once every 0.1 seconds:

```csharp
IEnumerator DoCheck()
{
    for (;;)
    {
        if (ProximityCheck())
        {
            Debug.Log("Enemy nearby!");
        }
        yield return new WaitForSeconds(0.1f);
    }
}
```

Start this in `Start()` or `Update()`:

```csharp
private void Start()
{
    StartCoroutine(DoCheck());
}
```

***

### 🖱 Input Event: Mouse Clicks

You can detect when a GameObject is clicked using `OnMouseDown()`:

```csharp
public class ClickHandler : TerraBehaviour
{
    private void OnMouseDown()
    {
        Debug.Log("GameObject clicked!");
        doSomething();
    }
}
```

{% hint style="warning" %}
&#x20;Make sure the GameObject has a **collider** component to receive click events.
{% endhint %}

***

### 💥 Collision Events

Detect object collisions using `OnCollisionEnter`. Combine this with an object variable to filter specific GameObjects.

```csharp
public class CollisionHandler : TerraBehaviour
{
    private GameObject targetObject;

    private void Start()
    {
        targetObject = GetGameObjectVariable("cube");
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject == targetObject)
        {
            Debug.Log("Collided with cube!");
        }
    }
}
```

***

### 🌐 Multiplayer Events

When using `TerraNetBehaviour` (instead of `TerraBehaviour`), two special methods become available:

```csharp
public override void OnNetworkSpawn()
{
    // Called when this object is spawned on the network
}

public override void OnNetworkDespawn()
{
    // Called when this object is removed from the network
}
```

Use these to initialize or clean up network-specific data.

***

### 📡 Broadcasts (Manual Handling)

In earlier versions of Terra Studio, there was an `OnBroadcasted()` method that responded to broadcast messages. This is **no longer supported**.

To implement custom broadcast behavior:

* Use shared variables or flags
* Poll for signals in `Update()` or trigger logic manually via coroutines or function calls
* Handle events using Unity-style component communication (`GetComponent`, method calls, etc.)

## Multiplayer-Specific Events

For multiplayer games using `TerraNetBehaviour`, there are special network lifecycle methods:

```csharp
public override void OnNetworkSpawn()
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

### 📡 Broadcasts (Manual Handling)

In earlier versions of Terra Studio, there was an `OnBroadcasted()` method that responded to broadcast messages. This is **no longer supported**.

To implement custom broadcast behavior:

* Use shared variables or flags
* Poll for signals in `Update()` or trigger logic manually via coroutines or function calls
* Handle events using Unity-style component communication (`GetComponent`, method calls, etc.)
