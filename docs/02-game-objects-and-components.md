# 2. Game Objects & Components

## Goal
Learn how to structure the things that exist in your game world.

---

## 2.1 The GameObject / Entity Concept

Almost every game has some form of **GameObject** (also called Entity, Actor, etc.).

A GameObject is a container that represents “something” in the world:
- Player
- Enemy
- Bullet
- Tree
- Trigger volume
- Camera

On its own it usually has very little behaviour — it holds components.

---

## 2.2 Composition over Inheritance

**Bad approach (deep inheritance):**
```text
GameObject
  └── Character
        └── Player
        └── Enemy
              └── FlyingEnemy
              └── GroundEnemy
```

This becomes rigid and hard to maintain.

**Better approach (composition):**
A GameObject has a list of **Components** that give it behaviour and data.

Examples of components:
- Transform (position, rotation, scale)
- SpriteRenderer / MeshRenderer
- Rigidbody / PhysicsBody
- Health
- PlayerInput
- AIController
- AudioSource

You build complex objects by combining simple components.

---

## 2.3 Transform Component

Almost every object needs a Transform:

- Position (x, y, z)
- Rotation
- Scale

It also often supports parent-child hierarchy so children move with their parent.

---

## 2.4 Simple Component Example (Conceptual)

```text
GameObject "Player"
├── Transform
├── SpriteRenderer
├── Rigidbody
├── Health
├── PlayerController
└── Animator
```

Each component only knows about its own responsibility.

---

## 2.5 Benefits of Component Architecture

- Flexible – mix and match behaviours
- Reusable – same Health component on player and enemies
- Easier to reason about
- Matches how modern engines (Unity, Unreal, Godot) work

---

## Key Takeaways
- Prefer composition (has-a) over deep inheritance (is-a)
- A GameObject is mostly a container
- Components give data and behaviour
- Transform is almost always present

---

## Practice Ideas
1. Design a Player object using only components (list them).
2. Design an Enemy and a Bullet the same way.
3. Think of a behaviour that would be hard with inheritance but easy with components.

---

## Next Step
→ [03. Input Handling](03-input-handling.md)
