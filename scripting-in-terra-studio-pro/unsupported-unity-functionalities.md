---
description: This page lists everything that is currently not supported in T#
---

# Terra Pro: Unsupported Functionalities

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

## **Serialized Fields**

\
The public variables and variables marked with \[SerializeField] are not functional in the new variant.\
Instead of using \[SerializeField], use the following methods to access variables:

|                                |                                                      |
| ------------------------------ | ---------------------------------------------------- |
| GetObjectVariable(string name) | Gets GameObject variable with the specified name     |
| GetIntVariable(string name)    | Gets integer variable with the specified name        |
| GetFloatVariable(string name)  | Gets float variable with the specified name          |
| GetBoolVariable(string name)   | Gets boolean variable with the specified name        |
| GetCurveVariable(string name)  | Gets AnimationCurve variable with the specified name |

#### Example Usage

```csharp
public class MyScript : TerraBehaviour
{
    // [SerializeField] won't work. Instead use the following
    private float moveSpeed;
    public GameObject target;
    
    private void Start()
    {
        // Use these getter methods instead:
        float moveSpeed = GetFloatVariable("moveSpeed");
        GameObject target = GetObjectVariable("target");
        
        // Your code logic using these variables
    }
}
```

Would you like me to integrate this with the other limitations we've already discussed?

Retry[Claude can make mistakes.\
Please double-check responses.](https://support.anthropic.com/en/articles/8525154-claude-is-providing-incorrect-or-misleading-responses-what-s-going-on)

\


3.7 Sonnet

## **Generic Methods**

Generic methods such as `GetComponent<T>`, `AddComponent<T>`, `FindObjectOfType<T>`, and similar methods involving generics are not supported in T#.

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

Using GetComponent immediately after instantiating now works when you enable the "Awake Init" boolean in the Terra Machine component.&#x20;

```csharp
GameObject obj = Instantiate(prefab);
Rigidbody rb = obj.GetComponent(typeof(Rigidbody)); // Will work if "Awake Init" is enabled in Terra Machine// This might not work immediately after Instantiate
```

If "Awake Init" is not enabled, component references might not be fully initialized when GetComponent is called immediately after Instantiate.

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

## **GetComponent Instantly After Instantiate**

You cannot use GetComponent immediately after instantiating

```csharp
GameObject obj = Instantiate(prefab);
Rigidbody rb = obj.GetComponent(typeof(Rigidbody)); // This might not work immediately after Instantiate
```

Due to the current structure of T#, calling `GetComponent` right after `Instantiate` may not work as expected because the mono behavior might not be fully initialized yet.

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

Generic Lists are not supported. Use TerraList for all list requirements:

For example,:&#x20;

```csharp
TerraList myList = new TerraList();
myList.Add(5);
int firstInt = (int)myList[0];

TerraList gameObjectList = new TerraList();
gameObjectList.Add(someGameObject);
GameObject firstObject = (GameObject)gameObjectList[0];

TerraList floatList = new TerraList();
floatList.Add(1.5f);
float firstItem = (float)floatList[0];
```

The following code, for instance is not supported because it is not natively supported in T#.

```csharp
List<float> myList = new List<float>(); // Not allowed in T#
myList.Add(1.5f);
float firstItem = myList[0];
```

## Unity Events as Coroutines

Converting Unity events into coroutines is not supported:

```csharp
IEnumerator OnCollisionEnter(Collision collision) { // Not allowed
    yield return new WaitForSeconds(1);
}

```

Instead, use regular event methods and start separate coroutines:

```csharp
void OnCollisionEnter(Collision collision) {
    StartCoroutine(CollisionCoroutine(collision));
}

IEnumerator CollisionCoroutine(Collision collision) {
    yield return new WaitForSeconds(1);
    // Your code here
}

```

## Enums

Custom enums are not supported in T#:

```csharp
enum GameState { // Not allowed
    Playing,
    Paused,
    GameOver
}

```

Instead, use integer constants or string identifiers:

```csharp
private const int STATE_PLAYING = 0;
private const int STATE_PAUSED = 1;
private const int STATE_GAMEOVER = 2;

```

## Switch Statements

Switch statements are not supported:

```csharp
switch (state) { // Not allowed
    case 0:
        // Do something
        break;
    default:
        // Do something else
        break;
}

```

Use if-else statements instead:

```csharp
if (state == 0) {
    // Do something
}
else {
    // Do something else
}

```

## Custom Scripts in Collections

Custom scripts in Lists or Dictionaries are not supported:

```csharp
List<MyCustomScript> scriptList = new List<MyCustomScript>(); // Not allowed
Dictionary<string, MyCustomScript> scriptDict = new Dictionary<string, MyCustomScript>(); // Not allowed

```

Instead, use GameObject or Component references and get the scripts when needed:

```csharp
List<GameObject> objectList = new List<GameObject>();
// Get the script component when needed
MyCustomScript script = objectList[0].GetComponent(typeof(MyCustomScript)) as MyCustomScript;

```

## LINQ Libraries

LINQ operations are not supported:

```csharp
var filtered = myList.Where(x => x > 5).ToList(); // Not allowed

```

Use traditional loops instead:

```csharp
List<int> filtered = new List<int>();
for (int i = 0; i < myList.Count; i++) {
    if (myList[i] > 5) {
        filtered.Add(myList[i]);
    }
}

```

## Structs in TerraList

Custom structs cannot be stored in TerraList:

```csharp
TerraList structList = new TerraList();
structList.Add(new MyStruct()); // Not allowed

```

## TryGetComponent

TryGetComponent method is not supported:

```csharp
if (gameObject.TryGetComponent(typeof(Rigidbody), out Rigidbody rb)) { // Not allowed
    // Use rb
}

```

Use GetComponent instead with null checking:

```csharp
Rigidbody rb = gameObject.GetComponent(typeof(Rigidbody)) as Rigidbody;
if (rb != null) {
    // Use rb
}

```

## Try-Catch Blocks

Exception handling using try-catch blocks is not supported:

```csharp
try { // Not allowed
    // Some code
}
catch (Exception e) {
    // Handle error
}

```

## Partial Classes

Partial class definitions are not supported:

```csharp
partial class MyScript : MonoBehaviour { // Not allowed
    // Code
}

```

## Vector3 Boxing

Boxing operations for Vector3 are not supported:

```csharp
object boxedVector = (object)Vector3.zero; // Not allowed
Vector3 unboxedVector = (Vector3)boxedVector; // Not allowed

```

## Invoke Methods

The Invoke and InvokeRepeating methods are not supported:

```csharp
Invoke("MethodName", 2.0f); // Not allowed
InvokeRepeating("MethodName", 0f, 1.0f); // Not allowed

```

Use coroutines instead:

```csharp
StartCoroutine(InvokeWithDelay());

IEnumerator InvokeWithDelay() {
    yield return new WaitForSeconds(2.0f);
    MethodName();
}

```

## Action Parameters

Actions are limited to a maximum of 4 parameters:

```csharp
Action<int, int, int, int, int> myAction; // Not allowed (more than 4 parameters)

```

## IPointer Events

Interface implementations for pointer events are not supported:

```csharp
public class MyScript : MonoBehaviour, IPointerClickHandler { // Not allowed
    public void OnPointerClick(PointerEventData eventData) {
        // Code
    }
}

```

## PlayerPrefs

Unity's PlayerPrefs system is now fully supported:

```csharp
PlayerPrefs.SetInt("Score", 100); // Allowed
int score = PlayerPrefs.GetInt("Score"); // Allowed
PlayerPrefs.Save(); // Allowed
// All PlayerPrefs methods work as they do in standard Unity

```

## **Unity Lifecycle Methods**

Several Unity lifecycle methods are not supported or may have limited functionality:

```csharp
void OnEnable() { // May not work as expected
    // Code
}

void OnDisable() { // May not work as expected
    // Code
}

void OnDestroy() { // May not work as expected
    // Code
}

void LateUpdate() { // Not supported
    // Code
}

```

Use Start, Update, and custom methods instead, and manage object lifecycle manually when needed.

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
