---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Multiplayer Support Differences

## 🌐  `NetworkBehaviour` versus `TerraNetBehaviour`

For multiplayer games, Unity devs might use `NetworkBehaviour` from Netcode for GameObjects or Mirror.  In Terra Studio, **you must use `TerraNetBehaviour` instead**. It provides network-specific lifecycle methods & wrappers for multiplayer-enabled GameObjects.

```csharp
public class MyMultiplayerScript : TerraNetBehaviour {
    public override void OnNetworkSpawn() {
        // Code for when object spawns on the network
    }

    public override void OnNetworkDespawn() {
        // Code for when object despawns from the network
    }
}
```

***



## COLLECTIONS & TYPES

### 🧾 Dictionaries

In Unity, `Dictionary<TKey, TValue>` is used to store and quickly access data using keys — it's a common tool for lookups, mapping, and efficient access patterns. This pattern is not supported in T#.

```csharp
Dictionary<string, int> myDict = new Dictionary<string, int>();
```

🔁 **What you instead need to do in T# to use key-value pairs:**\
Use `TerraDictionary`, which is interpreter-compatible.

```csharp
TerraDictionary myDict = new TerraDictionary();
myDict.Add("key1", 1);

int value = (int)myDict["key1"]; // ✅ Works
```

***

### 📋 Lists

In Unity, `List<T>` is the go-to for dynamic arrays — it's used to manage growing or shrinking collections of elements like GameObjects, positions, and more. This approach is not supported in T#.

```csharp
List<float> myList = new List<float>();
myList.Add(1.5f);
float firstItem = myList[0];
```



🔁 **What you instead need to do in T# to work with dynamic collections:**\
Use `TerraList`, which works the same way but is compatible with T#.

```csharp
TerraList myList = new TerraList();
myList.Add(5);
int firstInt = (int)myList[0];

TerraList gameObjectList = new TerraList();
gameObjectList.Add(someGameObject);
GameObject firstObject = (GameObject)gameObjectList[0];
```

### 📦 Structs in TerraList

In Unity, structs are often used for lightweight data containers, and it’s common to store them in collections. This is not supported in T#.

```csharp
TerraList structList = new TerraList();
structList.Add(new MyStruct()); // ❌
```

🔁 **What you instead need to do in T#:**\
Avoid storing custom structs in `TerraList`.Only primitive types (like `int`, `float`, `bool`) or supported objects (e.g., `GameObject`) should be added.

### 🧩 Custom Scripts in Collections

In Unity, it's common to store custom script instances inside `List<T>` or `Dictionary<TKey, TValue>` for managing multiple game behaviors. This is not supported in T#.

```csharp
List<MyCustomScript> scriptList = new List<MyCustomScript>();
Dictionary<string, MyCustomScript> scriptDict = new Dictionary<string, MyCustomScript>();
```

🔁 **What you instead need to do in T#:**\
Use `GameObject` references and access the components as needed.

```csharp
List<GameObject> objectList = new List<GameObject>();
MyCustomScript script = objectList[0].GetComponent(typeof(MyCustomScript)) as MyCustomScript;
```

### 🧮 LINQ Libraries

Unity developers often use LINQ (`.Where()`, `.ToList()`, etc.) for elegant data filtering and querying collections. This is not supported in T#.

```csharp
var filtered = myList.Where(x => x > 5).ToList();
```

🔁 **What you instead need to do in T#:**\
Use traditional loops to filter or transform data.

```csharp
List<int> filtered = new List<int>();
for (int i = 0; i < myList.Count; i++) {
    if (myList[i] > 5) {
        filtered.Add(myList[i]);
    }
}
```

***

## INPUT & UI

### 🖱️ IPointer Events

In Unity’s UI system, interfaces like `IPointerClickHandler` are used to detect and respond to user input events like button clicks or hovers. This is not supported in T#.

```csharp
public class MyScript : MonoBehaviour, IPointerClickHandler {
    public void OnPointerClick(PointerEventData eventData) {
        // Handle click
    }
}
```

🔁 **What you instead need to do in T# to detect user input:**\
Use manual input checks inside `Update()` or `OnMouseDown()` if available.

```csharp
void Update() {
    if (Input.GetMouseButtonDown(0)) {
        // Perform raycast or bounds check to detect a click
        HandleClick();
    }
}

void HandleClick() {
    Debug.Log("Custom click logic triggered.");
}
```

### 🎞️ DOTween for UI Animations

DOTween is widely used in Unity for smooth tween-based animations but DOTween is only partially supported in T#.&#x20;

#### 🔁 What works in T#:

Basic one-liners like this are supported:

```csharp
transform.DOMoveX(5, 2f); // ✅ Simple implementaiton like this works
```

{% hint style="warning" %}
Advanced features like custom `Tweeners`, complex `Sequences`, and chaining may not work:

```
Sequence s = DOTween.Sequence(); // ❌ Limited or unsupported
s.Append(...);
```
{% endhint %}

### ASYNC & REFLECTION

### **❌ `async` / `await`**

In Unity, asynchronous methods using `async Task` are often used for non-blocking workflows. This is not supported in T# .&#x20;

```csharp
async Task MyAsyncMethod() {
    await SomeTask();
}
```

.

🔁 **What you instead need to do in T#:**\
Use coroutines for delays or async-like behavior.

```csharp
void Start() {
    StartCoroutine(MyCoroutine());
}

IEnumerator MyCoroutine() {
    yield return new WaitForSeconds(1f);
    // Continue logic
}
```

***

### **❌ `Task.Run()`**

Unity developers sometimes use `Task.Run` to offload work to background threads. This is not supported in T#.

```csharp
Task.Run(() => {
    // Heavy operation
});
```

🔁 **What you instead need to do in T#:**\
T# is single-threaded. Keep logic lightweight and frame-safe. You can Break tasks into smaller operations in `Update()` or use coroutines for pacing.

***

**❌ `GetType()` or `typeof()`**

In Unity, these are used for reflection, dynamic behavior, or type comparisons. These are not supported in T#.

```csharp
Type type = GetType(); // Not supported
Type componentType = typeof(Rigidbody); // Not supported
```

🔁 **What you instead need to do in T#:**\
Instead of **`GetType()` or `typeof(),`** you need to use direct type references and avoid dynamic type inspection.

## MISCELLANEOUS

### 📦 Unboxing

Unboxing is used in Unity when working with values stored as `object`, especially when dealing with collections, reflection, or generic types. Developers commonly cast the object back to its original type for reuse. However, **direct unboxing via casting is not supported in T#**.

```csharp
object boxedVal = (int)3;
int value = (int)boxedVal; // ❌ Not supported in T#
```

🔁 **What you instead need to do in T# to avoid direct unboxing:**\
Use `Convert` methods to safely extract values from boxed objects.

```csharp
object boxedVal = (int)3;
int value = Convert.ToInt32(boxedVal); // ✅ Works in T#
```

### 🧪 TryGetComponent

Unity provides `TryGetComponent` for safe and efficient component lookup. This is not supported in T#.

```csharp
if (gameObject.TryGetComponent(typeof(Rigidbody), out Rigidbody rb)) {
    // Use rb
}
```

🔁 **What you instead need to do in T#:**\
Use `GetComponent` with a null check.

```csharp
Rigidbody rb = gameObject.GetComponent(typeof(Rigidbody)) as Rigidbody;
if (rb != null) {
    // Use rb
}
```

***

### 🧯 Try-Catch Blocks

In Unity C#, `try-catch` blocks are commonly used to handle runtime exceptions gracefully — such as null references, invalid casts, or file errors — without crashing the game. This is not supported in T#.

```csharp
try {
    //Some Code
}
catch (Exception e) {
    Debug.Log("Something went wrong: " + e.Message);
}

```

🔁 **What you instead need to do in T#:**\
Use conditionals or null checks to avoid invalid operations and prevent exceptions. This approach keeps your code safe **without relying on exception handling**, which isn't supported in the interpreted T# runtime.

```csharp
object someObject = GetVariable("someValue");

if (someObject != null && someObject is int) {
    int value = (int)someObject;
    // Safe to use value
} else {
    Debug.Log("Invalid or missing value.");
}
```

***

### 📂 Partial Classes

Unity supports `partial` classes to split class definitions across multiple files, useful in generated code or large systems. This is not supported in T#.

🔁 **What you instead need to do in T#:**\
Keep all your class code in a single file.

{% hint style="danger" %}
Never split class definitions across multiple files when using T#. Keep all class code in a single file
{% endhint %}

***

### 🧱 Vector3 Boxing

In Unity, it's common to **box value types** like `Vector3` into `object` variables — especially when working with generic containers or loose data storage. This is not supported in T# .

```csharp
object boxedVector = (object)Vector3.zero;
Vector3 unboxed = (Vector3)boxedVector;
```

🔁 **What you instead need to do in T# to work with Vector3 values:**\
Avoid boxing. Always use `Vector3` in **strongly typed variables** and avoid casting through `object`. If you need to pass `Vector3` around generically (like in a list), store it only in structures that natively support `Vector3` — not as `object`.

```csharp
Vector3 position = new Vector3(0, 0, 0); // ✅ Typed usage is safe
transform.position = position;
```

***

### 🔢 Action Parameters

In Unity, `Action<T1, T2, ..., Tn>` is often used for event-driven systems, allowing you to pass multiple arguments in callbacks. This is not supported in T# , as `Action` is limited to **4 parameters**.

```csharp
Action<int, int, int, int, int> myAction; // ❌ More than 4 parameters
```

🔁 **What you instead need to do in T# to support custom callbacks:**\
Limit your `Action` definitions to **4 or fewer parameters**, or refactor the logic to group parameters.

```csharp
Action<int, int, int, int> onPlayerStatUpdate; // ✅ Allowed

// Or refactor into a single object if needed:
public class PlayerStats {
    public int health;
    public int stamina;
    public int energy;
    public int level;
    public int score;
}

// Use one parameter:
Action<PlayerStats> onStatsChanged;
```

***

## PLAYER PREFS

Unity's PlayerPrefs system is now fully supported:

```csharp
PlayerPrefs.SetInt("Score", 100); // Allowed
int score = PlayerPrefs.GetInt("Score"); // Allowed
PlayerPrefs.Save(); // Allowed
// All PlayerPrefs methods work as they do in standard Unity

```
