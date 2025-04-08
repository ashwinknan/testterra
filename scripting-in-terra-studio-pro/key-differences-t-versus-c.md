---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Key Differences - T# versus C\#

## 🔍 What's Different in T#?

While T# is designed to feel instantly familiar to Unity C# developers, there are a few **important differences** to keep in mind. These tweaks exist to support the interpreted nature of T# and ensure smoother live editing inside Terra Studio.

Most of your Unity habits will carry over just fine — but for the few edge cases, here's what you need to adjust:

### 🧠 MonoBehaviour vs TerraBehaviour

In Unity, scripts connect to the engine by extending the built-in `MonoBehaviour` class. This allows the script to be attached to GameObjects and use lifecycle methods like `Start()` and `Update()`. T# scripts , however, don't inherit from the `Monobehaviour` Class.&#x20;

{% hint style="danger" %}
&#x20;In T#, do not inherit from `MonoBehaviour`. It is unsupported and will prevent your script from working.
{% endhint %}

```csharp
public class MyFirstScript : MonoBehaviour {
    void Start() {
        // Initialization logic
    }

    void Update() {
        // Per-frame logic
    }
}
```

🔁 **What you instead need to do in T#:**\
All scripts must derive from `TerraBehaviour` ( (or `TerraNetBehaviour` in case of multiplayer games) instead of `MonoBehaviour`. This is the base class recognized by Terra Studio’s runtime for regular game scripts.

```csharp
public class MyFirstScript : TerraBehaviour {
    void Start() {
        // Initialization logic
    }

    void Update() {
        // Per-frame logic
    }
}

```

{% hint style="success" %}
All scripts in T# must inherit from either `TerraBehaviour` (for single-player logic) or `TerraNetBehaviour` (for multiplayer features), depending on the game type.
{% endhint %}

### 🌐 Multiplayer: `NetworkBehaviour` versus `TerraNetBehaviour`

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

### 🛠️ Default Variable Assigning

In Unity, it's common (and convenient) to assign default values to variables directly when declaring them. However, this pattern is **not supported in T#** if the value is assigned outside a method.

```csharp
private string var1 = "hello world"; // ❌ Not allowed in T#
void Start() {
    // Do something
}
```

🔁 **What you instead need to do in T# to avoid inline assignment:**\
Always initialize variables _inside_ a method like `Start()`.

```csharp
private string var1;

void Start() {
    var1 = "hello world"; // ✅ Allowed since you are assigning the value for the variable  within a method
}
```

***

### 🎛️ Serialized Fields

In Unity, developers often use `public` or `[SerializeField]` fields to expose values in the Inspector. This lets you easily assign GameObjects, floats, and other data through the Unity Editor.This allows you to assign values directly in the Unity Editor but this method isn't supported in T#.

```csharp
public float moveSpeed;
[SerializeField] private GameObject target;
```

🔁 **What you instead need to do in T# to access Inspector-like values:**

T# doesn’t support `public` fields or `[SerializeField]`. Use built-in variable getter methods instead.

👉 Instead, use the built-in variable getters like the followin&#x67;**:**

| Variable Getter                  | Description                                          |
| -------------------------------- | ---------------------------------------------------- |
| `GetObjectVariable(string name)` | Gets GameObject variable with the specified name     |
| `GetIntVariable(string name)`    | Gets integer variable with the specified name        |
| `GetFloatVariable(string name)`  | Gets float variable with the specified name          |
| `GetBoolVariable(string name)`   | Gets boolean variable with the specified name        |
| `GetCurveVariable(string name)`  | Gets AnimationCurve variable with the specified name |

```csharp
// This is allowed in T# since you are using variable getters instead of using Serialized Fields
private float moveSpeed;
private GameObject target;

void Start() {
    moveSpeed = GetFloatVariable("moveSpeed");
    target = GetObjectVariable("target");
}
```

***

### 🧬 Generic Methods

Unity supports generic methods like `GetComponent<T>()`, `AddComponent<T>()`, and `FindObjectOfType<T>()` for flexible and type-safe component handling. These are popular for writing clean, reusable code. However, Generic versions of Unity methods like  `GetComponent<T>`, `AddComponent<T>`, `FindObjectOfType<T>`, and similar methods involving generics are not supported in T#.

None of the following generic methods are supporte&#x64;**:**

```csharp
Rigidbody rb = gameObject.GetComponent<Rigidbody>();            // Not allowed
Rigidbody[] rbs = gameObject.GetComponents<Rigidbody>();        // Not allowed
gameObject.AddComponent<Rigidbody>();                           // Not allowed
Rigidbody rb = FindObjectOfType<Rigidbody>();                   // Not allowed
Rigidbody[] rbs = FindObjectsOfType<Rigidbody>();               // Not allowed
Rigidbody rb = GetComponentInParent<Rigidbody>();               // Not allowed
Rigidbody[] rbs = GetComponentsInParent<Rigidbody>();           // Not allowed
Rigidbody rb = GetComponentInChildren<Rigidbody>();             // Not allowed
Rigidbody[] rbs = GetComponentsInChildren<Rigidbody>();         // Not allowed
```

🔁 **What you instead need to do in T# to work with components:**

Instead, in T#, non-generic alternatives should be used such as the following:

```csharp
// Example of how to use GetComponent without generics
Rigidbody rb = (Rigidbody)gameObject.GetComponent(typeof(Rigidbody)) as Rigidbody;
```

***

### 🔁 `foreach` Loops

`foreach` is a clean and readable way to iterate over children or elements in a collection without worrying about indexing. It’s especially popular when working with `Transform`, `GameObject`, or any `IEnumerable`. However, `foreach` is not supported in T#.&#x20;

<pre class="language-csharp"><code class="lang-csharp">foreach (Transform child in transform) {
<strong>    // Do something
</strong>}
</code></pre>

**🔁 What you instead need to do in T# to avoid** `foreach`**:**

T# currently doesn’t support `foreach`, so always use a classic `for` loop when working with collections or child transforms.

```csharp
for (int i = 0; i < transform.childCount; i++) {
    Transform child = transform.GetChild(i);
    // Do something
}
```

***

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

***

### 🧪 GetComponent after Instantiate

In Unity, it’s common to `Instantiate` a prefab and immediately call `GetComponent<T>()` to modify or configure a component. This pattern is popular for initializing scripts or physics behaviors right after spawning an object. **In T#, this only works under a specific condition.**

```csharp
GameObject obj = Instantiate(prefab);
Rigidbody rb = obj.GetComponent<Rigidbody>(); // ❌ Not supported as-is
```

🔁 **What you instead need to do in T# to get a component after Instantiate:**\
Use the non-generic version of `GetComponent` with `typeof` and an explicit cast.

```csharp
GameObject obj = Instantiate(prefab);
Rigidbody rb = (Rigidbody)obj.GetComponent(typeof(Rigidbody)); // ✅ Works only if "Awake Init" is ON
```

{% hint style="warning" %}
Even when using the non-generic GetComponent, make sure “Awake Init” is enabled if calling it immediately after Instantiate().
{% endhint %}

### ⏳ Coroutines in `Start`

In Unity, you can define `Start()` as a coroutine (`IEnumerator`) to handle initialization steps with delays or wait conditions. This pattern is not supported in T#.

```csharp
Enumerator Start() {
    yield return new WaitForSeconds(1); // Waits before continuing
}
```

🔁 **What you instead need to do in T# to use coroutines at startup:**\
Use a regular `void Start()` method and trigger a coroutine from there.

```csharp
void Start() {
    StartCoroutine(MyCoroutine());
}

IEnumerator MyCoroutine() {
    yield return new WaitForSeconds(1); // ✅ Works
    // Your code here
}
```

***

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

***

### ⚡ Unity Events as Coroutines

In Unity, developers sometimes write event callbacks (like `OnCollisionEnter`) as coroutines to introduce delays directly within the event flow. This technique is not supported in T#.

```csharp
IEnumerator OnCollisionEnter(Collision collision) {
    yield return new WaitForSeconds(1);
    // Continue logic
}
```

🔁 **What you instead need to do in T# to delay event-based logic:**\
Instead, use a normal event method and start a coroutine from it.

```csharp
void OnCollisionEnter(Collision collision) {
    StartCoroutine(CollisionCoroutine(collision)); // ✅ Works
}

IEnumerator CollisionCoroutine(Collision collision) {
    yield return new WaitForSeconds(1);
    // Your delayed logic here
}
```

***

### 🎮 Enums

In Unity, developers often use `enum` to define named states or categories for readability and cleaner switch logic.This is not supported in T#.

```csharp
enum GameState {
    Playing,
    Paused,
    GameOver
}
```

🔁 **What you instead need to do in T# to represent states:**\
Use constants (`int` or `string`) to represent each state.

```csharp
private const int STATE_PLAYING = 0;
private const int STATE_PAUSED = 1;
private const int STATE_GAMEOVER = 2;
```

***

### 🔄 Switch Statements

In Unity, `switch` statements are a clean way to handle multiple branches based on an integer, enum, or string value. This is not supported in T#.

```csharp
switch (state) {
    case 0:
        // Do something
        break;
    default:
        // Fallback logic
        break;
}
```

🔁 **What you instead need to do in T#:**\
Use `if-else` chains to replicate switch behavior.

```csharp
if (state == 0) {
    // Do something
}
else {
    // Fallback logic
}
```

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

### 📦 Structs in TerraList

In Unity, structs are often used for lightweight data containers, and it’s common to store them in collections. This is not supported in T#.

```csharp
TerraList structList = new TerraList();
structList.Add(new MyStruct()); // ❌
```

🔁 **What you instead need to do in T#:**\
Avoid storing custom structs in `TerraList`.Only primitive types (like `int`, `float`, `bool`) or supported objects (e.g., `GameObject`) should be added.

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

### ⏲️ Invoke Methods

Unity provides `Invoke()` and `InvokeRepeating()` to call methods after a delay or repeatedly without needing coroutines. These are not supported in T#.

```csharp
Invoke("MethodName", 2.0f);
InvokeRepeating("MethodName", 0f, 1.0f);
```

🔁 **What you instead need to do in T#:**\
Use coroutines to delay method calls.

```csharp
StartCoroutine(InvokeWithDelay());

IEnumerator InvokeWithDelay() {
    yield return new WaitForSeconds(2.0f);
    MethodName();
}
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

***

## PlayerPrefs

Unity's PlayerPrefs system is now fully supported:

```csharp
PlayerPrefs.SetInt("Score", 100); // Allowed
int score = PlayerPrefs.GetInt("Score"); // Allowed
PlayerPrefs.Save(); // Allowed
// All PlayerPrefs methods work as they do in standard Unity

```

***

### 🔄 Unity Lifecycle Methods

In Unity, lifecycle methods like `OnEnable`, `OnDisable`, `OnDestroy`, and `LateUpdate` are commonly used to manage object states and time-sensitive operations. These methods are not supported  in T#.&#x20;

```csharp
void OnEnable() {
    // Initialization logic
}

void OnDisable() {
    // Clean-up logic
}

void OnDestroy() {
    // Final teardown
}

void LateUpdate() {
    // Execute after Update
}
```

.

🔁 **What you instead need to do in T#:**\
Use `Start()` and `Update()` for most logic, and manage lifecycle events manually using flags or custom methods. For delayed or post-frame execution, use coroutines instead of `LateUpdate()`.

```csharp
bool isInitialized = false;

void Start() {
    isInitialized = true;
    // Initialization logic
}

void Update() {
    if (!isInitialized) return;

    // Game loop logic
    if (shouldCleanup) {
        Cleanup();
    }
}

void Cleanup() {
    // Manual cleanup logic
}
```

***

### ⚙️ Miscellaneous Limitations

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
