---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Restrictions on Input, UI, Async

This section rounds up all input-related limitations, asynchronous code restrictions, and other notable Unity patterns that are not supported in T#. It also covers UI events, reflection methods, and a few important workarounds.

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

## ASYNC & REFLECTION

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

***
