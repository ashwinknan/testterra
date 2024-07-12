---
description: While T# is pretty similar to C#, somethings don't work the same
---

# What not to do on T\#

#### Things that do not work at all currently

1. Any form of Generic GetComponent\<T> or similar in which T is not defined in the game assembly. All of these have non generic working alternatives except AddComponent.
   1. `GetComponent<T>`
   2. `GetComponents<T>`
   3. `AddComponent<T> // even the non generic one isn't allowed currently`
   4. `FindObjectOfType<T>`
   5. `FindObjectsOfType<T>`
   6. `GetComponentInParent<T>`
   7. `GetComponentsInParent<T>`
   8. `GetComponentInChildren<T>`
   9. `GetComponentsInChildren<T>`
2. Enumerable on Transform
   1. This is a problem currently in interpreter. We can ask for a fix or try fixing ourselves.
   2. Can be overcome by using a for loop, in combination with `transform.childCount` and `transform.GetChild(i)`
3. foreach loops
   1. Foreach loops are currently disabled.
4. Lambdas, delegates, Actions, Events, Funcs, UnityEvents
   1. The generic versions are the problem mostly. I don't think these are solvable unless (read : next section Pt1)
   2. The non generic ones need to be tested.
5. Unboxing.
   1. This is a problem currently in interpreter. We can ask for a fix or try fixing ourselves. An actual fix might not be possible however due to language limitations. Unsure.
   2. Ex : `object boxedVal = (int)3; //no problem int failingUnboxedVal = (int)boxedVal; //doesn't work int workingUnboxedVal = Convert.ToInt32(boxedVal); //works`
6. Calling GetComponent instantly after Instantiate call
   1. Because of the current structure. Can be fixed with a change in structure.
   2. The parallel mono is actually created whenever the Start of any script on an object is called. If you use `GetComponent()` instantly after Instantiate, the mono does not exist yet.
7. SerializedFields
   1. They aren’t currently supported.
   2. The alternative is to use, ObjectVariables which is a component that gets auto added on every object which has a `TerraMachine`. You can add any `GameObject` references to this, and access them from a script using `GetObjectVariable(key)` and `SetObjectVariable(key)`
8. Turning Event Functions Into Coroutines
   1. In normal Unity, you can use `IEnumerator Start()` and make your Start function act as a coroutine. This is not possible with interpreter currently.
9. Obvious things that will not behave as expected however shouldn’t be required by games
   1. `async` code
   2. `Tasks`
   3. Anything related to `GetType()` or `typeof()`
