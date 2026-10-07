# 6. State Machines

## Goal
Organize complex behaviour into clear, manageable states.

---

## 6.1 What is a Finite State Machine (FSM)?

A Finite State Machine is a system that can be in one state at a time and can transition to other states when certain conditions are met.

Classic example – Player:

```text
Idle ──→ Run ──→ Jump ──→ Fall ──→ Idle
  ↑                           │
  └───────────────────────────┘
```

---

## 6.2 Structure of a State

Each state usually has three main methods:

- **Enter** – called once when entering the state
- **Update** – called every frame while in the state
- **Exit** – called once when leaving the state

```text
class JumpState:
    Enter():
        play jump animation
        apply jump force

    Update(dt):
        if velocity.y < 0:
            change to FallState

    Exit():
        // cleanup if needed
```

---

## 6.3 Transitions

Transitions are conditions that move you from one state to another.

Examples:
- Idle → Run when horizontal input ≠ 0
- Run → Idle when horizontal input == 0
- Any → Jump when JumpPressed and IsGrounded
- Jump → Fall when velocity.y < 0

---

## 6.4 Player State Example

Common player states:
- Idle
- Run / Walk
- Jump
- Fall
- Attack
- Hurt / Knockback
- Dead

---

## 6.5 Enemy AI States

Typical enemy states:
- Idle / Patrol
- Chase
- Attack
- Return to spawn
- Die

---

## 6.6 Hierarchical State Machines (Advanced Intro)

Sometimes states contain sub-states (e.g. “OnGround” contains Idle and Run).  
This is useful for larger characters but not required at the beginning.

---

## Key Takeaways
- FSMs make behaviour readable and maintainable
- One state at a time
- Clear Enter / Update / Exit methods
- Transitions should be explicit

---

## Practice Ideas
1. Design a player state machine on paper.
2. Write pseudo-code for Idle, Run, and Jump states.
3. Design a simple enemy patrol → chase → attack FSM.

---

## Next Step
→ [07. Animation Logic](07-animation-logic.md)
