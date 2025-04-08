---
description: Enables Multiplayer experiences
---

# 🌐 Multiplayer in Terra Studio

**Terra Studio** supports full multiplayer capabilities using **Netcode for Unity** — Unity’s official networking solution for GameObjects ( **(see the full documentation  at** [**Unity Multiplayer Netcode Docs)**](https://docs-multiplayer.unity3d.com/netcode/1.10.0/about/). All standard Netcode workflows and components are supported directly, so if you’ve used Netcode before, you’re ready to go.

{% hint style="success" %}
Terra Studio uses ➡️ [Netcode for GameObjects – Unity Docs (v1.10.0)](https://docs-multiplayer.unity3d.com/netcode/1.10.0/about/)
{% endhint %}

***

## 🚀 Getting Started with Multiplayer

Just like with Unity, multiplayer scripts in Terra Studio derive from `NetworkBehaviour`. However, in Terra Studio, multiplayer scripts should **inherit from `TerraNetBehaviour`**, which wraps Unity's networking base class and is fully compatible with Netcode workflows.

### ✅ Basic Script Structure

```csharp
csharpCopyEditpublic class MyMultiplayerScript : TerraNetBehaviour
{
    // Code specific to this networked object

    // Called when the object is spawned on the network
    public override void OnNetworkSpawn()
    {
        // Initialization logic
    }

    // Called when the object is despawned from the network
    public override void OnNetworkDespawn()
    {
        // Cleanup logic
    }
}
```

These two lifecycle methods are useful for initializing and cleaning up your networked GameObjects.

***

## 🛠 Things to Keep in Mind

* Every GameObject you want to network must have a `NetworkObject` component.
* Any networked script must extend `TerraNetBehaviour` (not `MonoBehaviour` or `TerraBehaviour`).
* Refer to the Unity Netcode documentation for working with RPCs, ownership, spawning, synchronization, and more.

***

{% hint style="info" %}
Unity’s official Netcode documentation covers all essential multiplayer features you may need: ➡️ [Netcode for GameObjects – Unity Docs (v1.10.0)](https://docs-multiplayer.unity3d.com/netcode/1.10.0/about/)
{% endhint %}







***

###
