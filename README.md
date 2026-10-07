# Learning Game Development Logic

Repository for learning **core game development logic**, algorithms, design patterns, and systems.

This guide focuses on **language- and engine-independent** fundamentals that apply to any game (2D/3D, indie or AAA). Master these concepts and you can implement them in C++, C#, TypeScript, or any other language later.

---

## 1. Core Game Loop
- What is a game loop?
- Fixed vs variable timestep
- Delta time and frame-rate independence
- Update vs Render separation
- Simple loop structure (Input → Update → Render)

---

## 2. Game Objects & Components
- Entity / GameObject concept
- Composition over inheritance
- Component-based architecture (basics)
- Transform (position, rotation, scale)
- Hierarchy and parent-child relationships

---

## 3. Input Handling
- Polling vs event-based input
- Keyboard, mouse, and controller basics
- Action mapping (abstract actions instead of raw keys)
- Input buffering and edge detection (pressed / held / released)
- Simple input manager design

---

## 4. Movement & Physics Basics
- Velocity and acceleration
- Simple Euler integration
- Gravity and jumping
- Collision detection (AABB, Circle/Sphere)
- Collision response (separation, sliding)
- Raycasting (concept)

---

## 5. Time & Timing Systems
- Delta time usage
- Timers and cooldowns
- Delayed actions / scheduled events
- Time scaling (slow-motion, pause)
- Frame-rate independent logic

---

## 6. State Machines
- Finite State Machines (FSM)
- States, transitions, and conditions
- Player states (Idle, Run, Jump, Attack, etc.)
- Enemy AI states
- Hierarchical / nested state machines (introduction)

---

## 7. Animation Logic (Not Visuals)
- Animation states vs visual frames
- Animation events / callbacks
- Blending concepts (crossfade)
- Root motion vs in-place animation logic
- Syncing gameplay with animation

---

## 8. Camera Systems
- Follow camera (lerp / smooth damp)
- Look-at / targeting
- Camera bounds and clamping
- Screen shake (simple implementation)
- Multiple camera modes (overview)

---

## 9. UI & HUD Logic
- Separation of game logic and UI
- Event-driven UI updates
- Health bars, score, timers
- Menus and screen flow (state-based)
- Input blocking when UI is open

---

## 10. Game Data & Configuration
- Hard-coded vs data-driven design
- Using JSON / Scriptable data for stats, levels, items
- Loading and parsing game data
- Balancing and tuning values without recompiling

---

## 11. Saving & Loading
- What data should be saved?
- Serialization concepts
- Player progress, inventory, settings
- Versioning save data (basic awareness)

---

## 12. Common Design Patterns in Games
- Singleton (use carefully)
- Observer / Event system
- Object Pooling
- Command pattern (input replay, undo)
- State pattern
- Factory / Object creation

---

## 13. Basic AI Logic
- Simple decision making (if-else / switch)
- Patrol, chase, attack behaviours
- Sensing (distance checks, line-of-sight concept)
- Pathfinding awareness (A* concept only)
- Group behaviours (very basic)

---

## 14. Audio Logic (Not Sound Design)
- Sound triggers based on events
- Music state changes (explore / combat)
- Volume and mixing concepts
- 2D vs 3D audio positioning (logic side)

---

## 15. Optimization Mindset (Beginner Level)
- Avoid doing expensive work every frame
- Object pooling vs constant instantiation
- Spatial partitioning awareness (grids / quadtrees concept)
- Profiling mindset: measure before optimizing

---

## 16. Good Practices for Game Logic
- Keep gameplay code readable and modular
- Prefer composition
- Separate concerns (input, physics, AI, UI)
- Use clear naming for states and events
- Prototype fast, then clean up
- Always think in terms of systems, not just features

---

## Suggested Learning Path
1. Master the **Game Loop** and **Delta Time**
2. Build a simple moving character with input and basic physics
3. Add a Finite State Machine for player states
4. Implement simple collisions and camera follow
5. Create a basic enemy with patrol/chase states
6. Add data-driven stats (JSON) and a simple save system
7. Practice common patterns (events, object pooling)

---

## Recommended Practice Projects
- Top-down movement + camera follow
- Platformer prototype (jump, gravity, collision)
- Simple enemy AI with state machine
- Wave-based spawner with object pooling
- Inventory + item pickup system
- Pause menu + game state management

---

## Resources (Recommended)
- **Books**: *Game Programming Patterns* (Robert Nystrom) – free online
- **Articles**: Gaffer on Games (timestep), Game Programming Patterns website
- **Concepts**: Entity-Component-System (ECS) overview, Data-Oriented Design introduction
- **Practice**: Re-implement classic mechanics (Flappy Bird logic, Snake, simple shooter) from scratch

---

**Remember**:  
Game development is mostly **systems thinking**. Focus on clean, reusable logic that can later be plugged into Unity, Unreal, Godot, Three.js, or your own engine.

Happy building!
