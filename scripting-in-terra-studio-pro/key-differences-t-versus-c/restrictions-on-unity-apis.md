---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Restrictions on Unity APIs

While T# supports many of Unity’s APIs, **certain methods, lifecycle hooks, and behaviors are restricted**.\
These limitations exist due to the live-editing runtime and interpreted execution model of Terra Studio

### 🚫 LateUpdate

In Unity, `LateUpdate()` is often used to perform actions after all `Update()` calls — such as camera movement or following a character.**`LateUpdate()` is not supported in T#**.

#### 🔁 What you instead need to do in T#:

Use coroutines with `WaitForEndOfFrame()` to simulate end-of-frame logic.

```csharp
IEnumerator DelayedLogic() {
    yield return new WaitForEndOfFrame();
    // Logic that would have gone in LateUpdate
}
```

Call the coroutine when needed, for example in `Start()` or `Update()`:

```csharp
void Start() {
    StartCoroutine(DelayedLogic());
}
```

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
