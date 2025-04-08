---
icon: code
---

# Scripting Basics

## 🚀 Introducing T# (T-Sharp)

### 🛠️ What is T#?

**T#** is a custom programming language built for **Terra Studio**.\
At its core, **T# is an interpreted language**, meaning code is **read and executed directly** at runtime without needing a traditional compilation step.

### 💡 Why an Interpreter?

We designed T# to be interpreted because:

* **Fast Development Cycles**: Developers can instantly test and modify their code without waiting for builds or compilation.
* **Maximum Flexibility**: Code can be changed, extended, or scripted dynamically inside Terra Studio environments.
* **Better for Creativity**: Games, prototypes, and experiences can be tweaked and tuned live, unlocking faster iteration and experimentation.

Using an interpreter helps developers **stay in the flow** — write code, run it immediately, and see results without friction.

### ⚙️ How Does T# Work Under the Hood?

Here’s a high-level overview of what happens when you run T# code:

1. **Parsing**\
   The interpreter reads the T# source code line-by-line, breaking it into meaningful chunks like variables, functions, and classes.
2. **Syntax Validation**\
   It checks the code structure to ensure it follows T#'s (C#-like) rules. If something's wrong (like a missing semicolon), it immediately throws an error.
3. **Execution**\
   Once parsed and validated, each line or block of code is executed right away. There’s no intermediate `.exe` or separate build phase.
4. **Runtime Management**\
   The interpreter keeps track of variables, objects, and their states dynamically in memory while the application is running.

### 🔁 Familiar to Unity C# Developers

T# is designed with Unity developers in mind. If you've written MonoBehaviour scripts or managed game states in Unity, picking up T# will feel second nature. Many of the core concepts translate directly.

Here are a few examples to show how T# mimics Unity C#:

**✅ State Pattern (Unity-style):**

In Unity C#, a common way to handle player behavior is using states:

```csharp
public class IdlePlayerState : IState {
    private readonly Player player;
    public IdlePlayerState(Player newPlayer) {
        player = newPlayer;
    }

    public override void Start() {
        player.InitializeIdleState();
    }

    public override void Update() {
        player.UpdateIdleState();
    }
}
```

**T# Equivalent**\
In T#, you'd define a state in a similar way using classes and method overrides — no need to learn a new paradigm.

```tsharp
class IdlePlayerState : IState {
    Player player;

    IdlePlayerState(Player newPlayer) {
        player = newPlayer;
    }

    override Start() {
        player.InitializeIdleState();
    }

    override Update() {
        player.UpdateIdleState();
    }
}
```

***

**✅ Unity Input + Game Logic:**

In Unity C#:

```csharp
if (Input.GetKeyDown(KeyCode.F)) {
    SwapToNearestMovingPlayer(ballPosition);
}
```

**T# Equivalent**

```tsharp
if (Input.GetKeyDown("F")) {
    SwapToNearestMovingPlayer(ballPosition);
}
```

T# keeps the logic syntax clean and nearly identical, just trimming some of the boilerplate.

***

With T#, Unity devs can leverage their existing skills while building inside Terra Studio — write your scripts, hook into game events, and keep the same coding rhythm you're used to. 🚀
