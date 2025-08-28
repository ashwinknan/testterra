# Overview

Flow transforms your game project from static assets and code into a **living system** — patchable, observable, and improvable in real time. Instead of traditional development cycles that require builds, deployments, and downtime, Flow lets you modify, monitor, and enhance your game while players are actively using it.

### How Flow Works

Flow operates on two integrated layers:

**Foundation Layer**: Core infrastructure that makes your project "live" and "aware"&#x20;

**Assistant Layer**: Specialized AI tools that leverage the foundation to solve specific development tasks

The Foundation provides the underlying intelligence and capabilities. The Assistants use these capabilities to handle concrete development challenges like UI creation, performance debugging, and data analysis.

***

### Foundation Layer

Three core systems provide the intelligence and capabilities that every assistant depends on.

#### [🔥 Hot Deploy Engine](broken-reference)

Your core runtime deployment system that breaks the traditional build-deploy-test cycle.

* **Live Modifications**: Update scripts, assets, and UI elements directly for active players without requiring an app release
* **Real-Time Sync**: Keeps game state synchronized across all devices instantly
* **Zero Downtime**: Players experience changes seamlessly without interruption or restarts

#### [🗺 Asset Atlas (aka Project Context)](broken-reference)

A comprehensive knowledge graph that understands your entire project ecosystem.

* **Complete Indexing**: Maps every asset, script, prefab, shader, reference, and dependency in your project
* **Natural Language Queries**: Ask questions like "What assets are unused but packed?" or "Which prefabs reference this shader?" and get immediate answers
* **Contextual Intelligence**: Powers advanced features like automatic summarization and flow diagrams for economy, design, and monetization systems

#### [⚡ WirePilot](broken-reference)

An intelligent system for automatic wiring and scaffolding that maintains your game's integrity as it grows.

* **Smart Detection**: Automatically identifies new fields, buttons, or systems and maps them to relevant objects
* **End-to-End Extension**: Seamlessly extends existing gameplay systems (inventory, resources, abilities) with new items while preserving functionality
* **Balance Preservation**: Ensures design curves and game balance remain intact when systems expand or evolve

***

### Assistant Layer

Specialized AI tools that handle specific development tasks. Each assistant uses the foundation layer to provide intelligent, context-aware solutions.

#### [🖼 UI Builder](broken-reference)

**Fast interface creation with automatic wiring**

Creates UI layouts and automatically handles connections between UI elements and your code. Uses WirePilot to wire UI elements to scripts and data, while Asset Atlas finds relevant prefabs, sprites, and animations.

#### [📊 Auto-Profiler](broken-reference)

**AI-powered performance debugging**

Captures runtime performance data from real player devices. When frame drops, memory leaks, or performance spikes occur, AI analysis identifies the most likely causes. Asset Atlas maps performance issues to specific assets and scripts, converting hours of log analysis into prioritized lists of problems to fix.

#### [📈 Analytics Ninja](broken-reference)

**Natural language telemetry queries**

Query your game's telemetry data using plain English. Ask questions like "Which levels have the highest quit rates?" and get visualized answers in seconds. Asset Atlas provides context by connecting telemetry metrics to actual game features and design decisions.

***

### How it all ties together

Flow is an integrated system where each component enhances the others:

* **UI Builder** uses Asset Atlas to find relevant assets and WirePilot to handle wiring automatically
* **Profiler** uses Asset Atlas to map performance issues directly to specific assets and scripts
* **Analytics Ninja** uses Asset Atlas to provide context for telemetry data, connecting metrics to actual game features
* **Hot Deploy Engine** enables all assistants to push changes instantly without downtime

This integration means each assistant has full knowledge of your project structure, dependencies, and systems. When you use any Flow tool, it understands your codebase and can make intelligent decisions about how changes should propagate through your game.
