---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Restrictions on Collections & Types

T# does not fully support complex C# data types like `Dictionary`, `List<T>`, or user-defined script collections.This section lists the **type system differences** and shows how to work with Terra-compatible collections instead

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

### 📦 Structs in TerraList

In Unity, structs are often used for lightweight data containers, and it’s common to store them in collections. This is not supported in T#.

```csharp
TerraList structList = new TerraList();
structList.Add(new MyStruct()); // ❌
```

🔁 **What you instead need to do in T#:**\
Avoid storing custom structs in `TerraList`.Only primitive types (like `int`, `float`, `bool`) or supported objects (e.g., `GameObject`) should be added.

***

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

***

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
