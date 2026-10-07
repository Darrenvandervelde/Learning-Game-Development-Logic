# 5. Time & Timing Systems

## Goal
Control time-related behaviour reliably.

---

## 5.1 Delta Time Recap

Almost every time-based calculation should use delta time so the game feels the same at different frame rates.

---

## 5.2 Timers and Cooldowns

Simple cooldown:

```text
float cooldownTimer = 0

Update(dt):
    if (cooldownTimer > 0)
        cooldownTimer -= dt

    if (WantToShoot && cooldownTimer <= 0)
    {
        Shoot()
        cooldownTimer = 0.5   // half second cooldown
    }
```

---

## 5.3 Delayed Actions

You often need to do something after a delay (“wait 1 second then explode”).

Two common approaches:
1. Simple timer variable
2. A more general timer / scheduler system that can run callbacks

---

## 5.4 Time Scaling (Slow-motion, Pause)

Many games support a time scale:

```text
realDelta = rawDeltaTime
gameDelta = rawDeltaTime * timeScale
```

- `timeScale = 1` → normal
- `timeScale = 0.5` → slow motion
- `timeScale = 0` → paused

UI and some systems may still use real (unscaled) time.

---

## 5.5 Pause

When paused you usually:
- Stop updating gameplay systems
- Still update UI and menus
- Optionally freeze physics

A clean way is to have different update groups or to check a global `IsPaused` flag.

---

## Key Takeaways
- Use delta time everywhere for gameplay
- Cooldowns and timers are extremely common
- Support time scale early if you want slow-motion or pause
- Separate scaled and unscaled time when needed

---

## Practice Ideas
1. Implement a simple cooldown for shooting.
2. Create a delayed action that prints a message after 2 seconds.
3. Design how pause would affect different systems in your game.

---

## Next Step
→ [06. State Machines](06-state-machines.md)
