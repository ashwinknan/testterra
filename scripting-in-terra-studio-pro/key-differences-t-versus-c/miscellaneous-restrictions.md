---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Miscellaneous Restrictions

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
