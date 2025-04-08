---
description: This page lists everything that is currently not supported in T#
icon: file-plus-minus
---

# Key Differences - T# versus C\#

While T# is designed to feel instantly familiar to Unity C# developers, there are a few **important differences** to keep in mind. These tweaks exist to support the interpreted nature of T# and ensure smoother live editing inside Terra Studio.

Most of your Unity habits will carry over just fine — but for the few edge cases, here's what you need to adjust:

## 🧾 1. Syntax Differences

**T# follows Unity C# syntax closely**, but some common programming patterns and language constructs are not supported due to the interpreted runtime.\
✅ Supported: `Start()`, `Update()`, typed variables\
❌ Not Supported: `foreach`, `switch`, `enum`, inline variable assignment, `SerializeField`, generics (`GetComponent<T>()`), etc.

➡️ See Full Syntax Differences in the link below →

{% content-ref url="syntax-differences-t-v-s-c.md" %}
[syntax-differences-t-v-s-c.md](syntax-differences-t-v-s-c.md)
{% endcontent-ref %}

***

## 🌐 2. Multiplayer Scripting

T# uses a different base class for networked behavior.\
**Unity's `NetworkBehaviour`** is replaced by **`TerraNetBehaviour`** in T#, and includes its own override methods like `OnNetworkSpawn()` and `OnNetworkDespawn()` for multiplayer object lifecycle management.

➡️ See Multiplayer Differences documentation here→

{% content-ref url="multiplayer-support-differences.md" %}
[multiplayer-support-differences.md](multiplayer-support-differences.md)
{% endcontent-ref %}



***

## 🔌 3. Unity API Restrictions

Certain Unity MonoBehaviour APIs are not available in T#, especially those involving advanced lifecycle hooks or reflection.

* ❌ Not Supported: `LateUpdate()`, `Invoke()`, `TryGetComponent()`, `GetComponent<T>()`, `OnCollisionEnter` as coroutine, `Start()` as coroutine, and more.
* ✔️ Workaround: Use coroutines manually (`StartCoroutine()`) and simulate delayed behavior with `WaitForSeconds()` or `WaitForEndOfFrame()`.\


➡️ See Unity API Restrictions  here →

{% content-ref url="restrictions-on-unity-apis.md" %}
[restrictions-on-unity-apis.md](restrictions-on-unity-apis.md)
{% endcontent-ref %}



***

## 🧱 4. Restrictions on Collections & Types

T# does not support C# generics-based collections like `List<T>`, `Dictionary<TKey, TValue>`, or LINQ queries.\
Instead, use Terra-compatible containers:

* ✅ `TerraList`
* ✅ `TerraDictionary`
* ❌ Avoid: storing custom scripts or structs in collections

➡️ See Collections & Types restrictions here→

{% content-ref url="restrictions-on-collections-and-types.md" %}
[restrictions-on-collections-and-types.md](restrictions-on-collections-and-types.md)
{% endcontent-ref %}



***

## 🎮 5. Input, UI & Miscellaneous Restrictions

Unity-specific interfaces like `IPointerClickHandler`, `Action` with more than 4 parameters, and try-catch blocks are unsupported in T#.\
Manual input handling and structured coroutines are your go-to alternatives. Also:

* ❌ `Vector3` boxing
* ❌ `partial` classes
* ✅ `PlayerPrefs` is fully supported (and integrated with Analytics)

➡️ See Input, UI & Misc Limitations →

{% content-ref url="restrictions-on-input-ui-async.md" %}
[restrictions-on-input-ui-async.md](restrictions-on-input-ui-async.md)
{% endcontent-ref %}

