# 1. Core Game Loop

## Goal
Understand the heartbeat of every game — the continuous cycle that keeps the game running.

---

## 1.1 What is a Game Loop?

A game loop repeatedly does three main things:

1. **Process Input** – Read keyboard, mouse, controller, etc.
2. **Update** – Advance game logic (movement, AI, physics, timers…)
3. **Render** – Draw the current state to the screen

This cycle runs as fast as possible (or at a fixed rate).

Pseudo-code:

```text
while (gameIsRunning)
{
    ProcessInput()
    Update(deltaTime)
    Render()
}
```

---

## 1.2 Delta Time

`deltaTime` is the time (in seconds) that passed since the last frame.

Using delta time makes your game **frame-rate independent**.

```text
position = position + velocity * deltaTime
```

Without delta time, the game runs faster on high refresh-rate monitors and slower on low ones.

---

## 1.3 Fixed vs Variable Timestep

### Variable Timestep
- Update with whatever `deltaTime` the frame took
- Simple to implement
- Can cause physics instability on very large or very small delta times

### Fixed Timestep
- Update logic at a constant rate (e.g. 60 times per second)
- Render as fast as possible
- More stable physics and deterministic behaviour

Common pattern (semi-fixed):

```text
accumulator += deltaTime

while (accumulator >= fixedDeltaTime)
{
    FixedUpdate(fixedDeltaTime)
    accumulator -= fixedDeltaTime
}

Render()
```

---

## 1.4 Separation of Update and Render

Never mix game logic and drawing in the same place when possible.

- **Update** → change data (positions, health, scores…)
- **Render** → only read data and draw it

This makes the code cleaner and easier to reason about.

---

## 1.5 Simple Implementation Outline

```text
Initialize()

while (running)
{
    float dt = CalculateDeltaTime()

    HandleInput()
    Update(dt)
    Render()
}

Shutdown()
```

---

## Key Takeaways
- The game loop is the foundation of every real-time game
- Always use delta time for movement and timers
- Prefer a fixed timestep for physics-heavy games
- Keep Update and Render separated

---

## Practice Ideas
1. Write a simple console “game loop” that prints a counter every frame (simulate delta time).
2. Make an object move at a constant speed using delta time.
3. Implement a basic fixed timestep accumulator.

---

## Next Step
→ [02. Game Objects & Components](02-game-objects-and-components.md)
