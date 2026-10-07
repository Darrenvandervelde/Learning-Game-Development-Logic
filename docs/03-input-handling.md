# 3. Input Handling

## Goal
Read player input cleanly and turn it into game actions.

---

## 3.1 Polling vs Event-based Input

**Polling** – Check the state every frame  
“Is the jump button currently held?”

**Event-based** – React when something happens  
“The jump button was just pressed.”

Most games use a combination of both.

---

## 3.2 Raw Input vs Actions

Never spread raw key codes throughout your code.

**Bad:**
```text
if (IsKeyPressed(Space))
    Jump()
```

**Better – Action Mapping:**
```text
if (IsActionPressed("Jump"))
    Jump()
```

You map physical keys/buttons to abstract actions in one place.

Example mapping:
- "Jump" → Space / Gamepad A
- "MoveHorizontal" → A/D or Left Stick X
- "Attack" → Left Mouse / Gamepad X

This makes rebinding controls easy later.

---

## 3.3 Input States

For digital buttons you usually care about three states:

| State       | Meaning                          |
|-------------|----------------------------------|
| Pressed     | Just went down this frame        |
| Held        | Currently down                   |
| Released    | Just went up this frame          |

Example:
```text
if (IsActionPressed("Jump"))   // only true on the frame it was pressed
if (IsActionHeld("Jump"))
if (IsActionReleased("Jump"))
```

---

## 3.4 Simple Input Manager Concept

A central place that:
1. Reads raw device input
2. Updates action states
3. Provides a clean API to the rest of the game

```text
Input.GetAction("Jump")        → bool (held)
Input.GetActionPressed("Jump") → bool
Input.GetAxis("Horizontal")    → float (-1 to 1)
```

---

## 3.5 Input Buffering (Useful Technique)

Players often press jump a few frames before landing.  
An input buffer remembers the press for a short time so the jump still happens when they become grounded.

---

## Key Takeaways
- Abstract input into actions
- Support Pressed / Held / Released
- Keep raw device code isolated in one place
- Consider buffering for responsive feel

---

## Practice Ideas
1. Design an action map for a simple platformer.
2. Write pseudo-code for an Input Manager.
3. Think about how you would handle both keyboard and gamepad.

---

## Next Step
→ [04. Movement & Physics Basics](04-movement-and-physics.md)
