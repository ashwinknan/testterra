---
description: While T# is pretty similar to C#, somethings don't work the same
---

# T# Don'ts

#### Things that do not work at all currently

1. Default variable assigning isn't allowed\
   &#x20;`private string var1 = "hello world"; // not allowed`                                  &#x20;
2. Any form of Generic GetComponent\<T> or similar in which T is not defined in the game assembly does not work in T#. (Note that All of these have non generic working alternatives except AddComponent )
   1. `GetComponent<T>`
   2. `GetComponents<T>`
   3. `AddComponent<T> // even the non generic one isn't allowed currently`
   4. `FindObjectOfType<T>`
   5. `FindObjectsOfType<T>`
   6. `GetComponentInParent<T>`
   7. `GetComponentsInParent<T>`
   8. `GetComponentInChildren<T>`
   9. `GetComponentsInChildren<T>`
3. Enumerable on Transform also does not currently work in the interpreter. This problem can be overcome by using a `for loop` , in combination with `transform.childCount` and `transform.GetChild(i)`
4. foreach loops are currently disabled.
5. Unboxing is a problem currently in interpreter. The examples below illustrate this.&#x20;

```csharp
object boxedVal = (int)3; //This works too
int workingUnboxedVal = Convert.ToInt32(boxedVal); // This works too
int failingUnboxedVal = (int)boxedVal; //This doesn't work
```

6. Calling GetComponent instantly after Instantiate call
   1. Because of the current structure. Can be fixed with a change in structure.
   2. The parallel mono is actually created whenever the Start of any script on an object is called. If you use `GetComponent()` instantly after Instantiate, the mono does not exist yet.
7. SerializedFields aren’t currently supported. The alternative is to use, ObjectVariables which is a component that gets auto added on every object which has a `TerraMachine`. You can add any `GameObject` references to this, and access them from a script using `GetObjectVariable(key)` and `SetObjectVariable(key)`
8. In normal Unity, you can use `IEnumerator Start()` and make your Start function act as a coroutine. Turning Event Functions Into Coroutines is not possible with interpreter.  This is not possible with interpreter currently.
9. Obvious things that will not behave as expected however shouldn’t be required by games
   1. `async` code
   2. `Tasks`
   3. Anything related to `GetType()` or `typeof()`
