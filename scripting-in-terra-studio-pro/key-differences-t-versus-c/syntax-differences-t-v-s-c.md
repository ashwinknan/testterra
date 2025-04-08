---
icon: file-plus-minus
---

# Syntax Differences - T# v/s C\#

This section covers **core language-level differences** in T# that affect how you write basic logic, class structures, and common C# patterns. These are **not Unity-specific**, but general constraints imposed by the T# interpreter.

## SYNTAX DIFFERENCES

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

{% hint style="danger" %}
None of the following generic methods are supported. Using them will always throw up an error

```
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
{% endhint %}

🔁 **What you instead need to do in T# to work with components:**

Instead, in T#, non-generic alternatives should be used such as the following:

```csharp
// Example of how to use GetComponent without generics
Rigidbody rb = (Rigidbody)gameObject.GetComponent(typeof(Rigidbody)) as Rigidbody;
```

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

### 🔄 Switch

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
