---
description: This page lists everything that is currently not supported in T#
---

# Unsupported Functionalities in T\#

## **Default Variable Assigning**

The following way of assigning default values is not supported in T#:

```csharp
private string var1 = "hello world"; // Not allowed in T#
```

Here's what you need to do instead:

```csharp
private string var1;

void Start() {
    var1 = "hello world"; // Allowed since you are assigning the value for the variable  within a method
}
```

## **Generic Methods**

Generic methods such as `GetComponent<T>`, `AddComponent<T>`, `FindObjectOfType<T>`, and similar methods involving generics are not supported in T#.

None of the following generic methods are supported**:**

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

**Alternative:** For most of these, non-generic alternatives should be used:

```csharp
// Example of how to use GetComponent without generics
Rigidbody rb = (Rigidbody)gameObject.GetComponent(typeof(Rigidbody)) as Rigidbody;
```

## **Iteration using foreach**

The following foreach loop will throw up an error as it is not Supported:

```csharp
//This is not allowed in T#
foreach (Transform child in transform) {
    // Do something
} 
```

Use a for loop instead as an alternative:

```csharp
// This is the right way to implement what you were trying to implement above
for (int i = 0; i < transform.childCount; i++) {
    Transform child = transform.GetChild(i);
    // Do something with child
}
```

## **Unboxing**

The following code is not supported:

```csharp
object boxedVal = (int)3;
int failingUnboxedVal = (int)boxedVal; // Not allowed
```

Instead, you can use this alternative:

```csharp
object boxedVal = (int)3;
int workingUnboxedVal = Convert.ToInt32(boxedVal); // Use Convert instead
```

## **GetComponent Instantly After Instantiate**

You cannot use GetComponent immediately after instantiating

```csharp
GameObject obj = Instantiate(prefab);
Rigidbody rb = obj.GetComponent(typeof(Rigidbody)); // This might not work immediately after Instantiate
```

Due to the current structure of T#, calling `GetComponent` right after `Instantiate` may not work as expected because the mono behavior might not be fully initialized yet.

## **SerializedFields**

The following code is not supported because it uses&#x20;

```csharp
[SerializeField] private GameObject obj; // Not allowed
```

Instead, use this alternative:

```csharp
// Use ObjectVariables component instead
ObjectVariables objVars = gameObject.GetComponent<ObjectVariables>();
objVars.SetObjectVariable("obj", someGameObject);

// Access it later
GameObject obj = objVars.GetObjectVariable("obj");
```

## **Coroutines in Start**

This way of starting Coroutines is not supported:

```csharp
IEnumerator Start() {
    yield return new WaitForSeconds(1);
    // Not allowed
}
```

Instead , use this alternative:

```csharp
void Start() {
    StartCoroutine(MyCoroutine());
}

IEnumerator MyCoroutine() {
    yield return new WaitForSeconds(1);
    // Your code here
}
```

## **Dictionary**

Use of Dictionary is not supported. The following way is not&#x20;

```csharp
Dictionary<string, int> myDict = new Dictionary<string, int>(); // Not allowed in T#

```

Use `TerraDictionary` as a substitute for dictionaries in T#. It provides similar functionality but is compatible with the interpreter.

```csharp
// This is compatible with T#
TerraDictionary myDict = new TerraDictionary();
myDict.Add("key1", 1);
int value = (int)myDict["key1"];
```

## **Lists**

Only certain list types, including `List<int>`, `List<string>`, `List<bool>`, `List<char>`, `List<GameObject>`, `List<Transform>`, `List<Vector3>`, `List<Vector2>`, `List<double>`, and `List<System.Single>`, are supported natively in T#. Use these directly without any issues.

For example, all of these work:&#x20;

```csharp
List<int> intList = new List<int>();
intList.Add(5);
int firstInt = intList[0];

List<GameObject> gameObjectList = new List<GameObject>();
gameObjectList.Add(someGameObject);
GameObject firstObject = gameObjectList[0];
```

The following code, for instance is not supported because it is not natively supported in T#.

```csharp
List<float> myList = new List<float>(); // Not allowed in T#
myList.Add(1.5f);
float firstItem = myList[0];
```

For unsupported list types such as the above, use `TerraList` instead of `List<T>`.

```csharp
TerraList myList = new TerraList();
myList.Add(1.5f);
float firstItem = (float)myList[0];
```

## **Miscellaneous**

Async  isn't supported

```csharp
async Task MyAsyncMethod() {
    await SomeTask(); // Not supported
}
```

Task isn't supported

```csharp
Task.Run(() => { /* Some code */ }); // Not supported
```

GetType() or typeof() isn't supported&#x20;

```csharp
Type myType = GetType(); // Not supported
```
