---
description: What is T#
---

# About T\#

T# is a scripting language developed by Terra. This was developed to provide developers who are used to writing code the flexibility to do almost anything on Terra's platforms. In Terra Studio 2.0, creators ability to make a variety of games was limited by the number of behavior blocks that were available in its library

T# removes this constraint. Now even if you don't have a behavior block in Terra Studio, you can go ahead and write your own script to make that happen.

## How to write your own script using T# &#x20;

If you want to add your own script to a particular object on Terra Studio, here is what you need to do:&#x20;

* Click on the Scripts tab on the left panel. It opens up the Scripts Panel
* Open up a new Script File by entering a file name and clicking the + sign next to it . You can select as much&#x20;
* You can attach the script by clicking on the Logic Tab and drag the Studio Machine behavior to the asset where you want to add the script
* In the contextual menu for Studio Machine, add the  script by selecting the correct script from the list of all scripts you have added so far
* Select the Visual Studio IDE on the Scripts Bar&#x20;
* Write the necessary script and save the script&#x20;
* &#x20;

## What happens under the hood

1. When you write C# code, it gets compiled into CIL (Common Intermediary Language) and stored in a DLL format in your library folder.
2. We read that DLL, which is basically a compiled list of instructions. When we want to execute something in the DLL, we find the method we want to execute and get its corresponding series of instructions.
3. Every possible instruction type (some are missing currently) has an implementation that we figure out. Its calling some or other functionality that’s already assumed to be defined in the app.
   1. If it exists in the app, and is a part of a binding table we’ve created before hand it executes the instruction using that. (These are called Direct Method Call Bindings)
   2. If it exists in the app, and is not part of the binding table, we search the app for a suitable method with Type, Class, Method Name & Signature. This lookup is slow as compared to the previous one.
   3. If it somehow doesn’t exist in the app, the execution halts.
   4. Any direct reference types that can be created via these instructions also need a parallel proxy written before hand for them. (These are called Proxies)

## Things that do not work at all currently

1.  Any form of Generic GetComponent\<T> or similar in which T is not defined in the game assembly. All of these have non generic working alternatives except AddComponent.

    * `GetComponent<T>`
    * `GetComponents<T>`
    * `AddComponent<T> // even the non generic one isn't allowed currently`
    * `FindObjectOfType<T>`
    * `FindObjectsOfType<T>`
    * `GetComponentInParent<T>`
    * `GetComponentsInParent<T>`
    * `GetComponentInChildren<T>`
    * `GetComponentsInChildren<T>`


2.  Enumerable on Transform

    * This is a problem currently in interpreter. We can ask for a fix or try fixing ourselves.
    * Can be overcome by using a for loop, in combination with `transform.childCount` and `transform.GetChild(i)`


3.  foreach loops

    * Foreach loops are currently disabled.


4.  Lambdas, delegates, Actions, Events, Funcs, UnityEvents

    * The generic versions are the problem mostly. I don't think these are solvable unless (read : next section Pt1)
    * The non generic ones need to be tested.


5. Unboxing
   * This is a problem currently in interpreter. We can ask for a fix or try fixing ourselves. An actual fix might not be possible however due to language limitations. Unsure.
   * Ex : `object boxedVal = (int)3; //no problem int failingUnboxedVal = (int)boxedVal; //doesn't work int workingUnboxedVal = Convert.ToInt32(boxedVal); //works`
   *   Calling GetComponent instantly after Instantiate call

       * Because of the current structure. Can be fixed with a change in structure.
       * The parallel mono is actually created whenever the Start of any script on an object is called. If you use `GetComponent()` instantly after Instantiate, the mono does not exist yet.


6.  Unboxing

    1. This is a problem currently in interpreter. We can ask for a fix or try fixing ourselves. An actual fix might not be possible however due to language limitations. Unsure.
    2. Ex : `object boxedVal = (int)3; //no problem int failingUnboxedVal = (int)boxedVal; //doesn't work int workingUnboxedVal = Convert.ToInt32(boxedVal); //works`


7. Calling GetComponent instantly after Instantiate call
   * Because of the current structure. Can be fixed with a change in structure.
   *   The parallel mono is actually created whenever the Start of any script on an object is called. If you use `GetComponent()` instantly after Instantiate, the mono does not exist yet.


8.  SerializedFields

    * They aren’t currently supported.
    * The alternative is to use, ObjectVariables which is a component that gets auto added on every object which has a `TerraMachine`. You can add any `GameObject` references to this, and access them from a script using `GetObjectVariable(key)` and `SetObjectVariable(key)`


9.  Turning Event Functions Into Coroutines



    In normal Unity, you can use `IEnumerator Start()` and make your Start function act as a coroutine. This is not possible with interpreter currently.


10. Obvious things that will not behave as expected however shouldn’t be required by games
    1. `async` code
    2. `Tasks`
    3. Anything related to `GetType()` or `typeof()`



## Things that we might need to add/fix :

1. If the fix for Funcs/delegates/actions/events/labdas/unity events work
   1. A combination of _all_ possible P\&C generic combinations of all types for all of the above Ex : `Action<int>, Action<uint>, Action<int,uint>, Action<uint,int>` are 4 possible combinations for two types
   2. Disallow generics in these also, and support only parameterless things.
2. AotList, AotArray, AotDictionary
   1. These might be a problem since unboxing is not allowed.
3. Object Variables (similar to Visual Scripting) OR, per Component Variables which will require a lot more effort

## Repercussions

1. Due to lack of serialized fields, you have to write a structured scene hierarchy approach and manage references via those or write some very basic level structure of dependency injection
2. Due to lack of un-boxing support, and the current architecture of Network Messages implemented in Interpreter by us (Commands, Client & Target Rpcs) you have to use System.Convert API to convert a boxed variable into its original type. `Convert.ToBool(someObject)` `Convert.ToInt32(someObject)` `Convert.ToUInt32(someObject)`

This is extremely error prone.

## Using SerializedFields

* Currently, SerializedFields aren’t supported in T#. (The feature where Unity lets you set fields of a script from the inspector itself)
* To work with this limitation, we have added a new Component called `ObjectVariables`
* This component gets auto-attached to any `StudioMachine`.
* You can use this to setup references, by giving a key and adding gameobject references to those keys.
* `instance GameObject GetObjectVariable(string key)`
* `instance SetObjectVariable(string key, GameObject toSet)`

