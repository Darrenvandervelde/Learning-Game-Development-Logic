# 4. Movement & Physics Basics

## Goal
Make objects move and interact with the world in a believable way.

---

## 4.1 Velocity and Acceleration

Basic movement:

```text
velocity = velocity + acceleration * deltaTime
position = position + velocity * deltaTime
```

This is simple Euler integration and is good enough for many games.

---

## 4.2 Gravity and Jumping

```text
// Apply gravity every frame
velocity.y += gravity * deltaTime

// Jump
if (IsGrounded && JumpPressed)
    velocity.y = jumpForce
```

Common values (starting points):
- Gravity: -20 to -30
- Jump force: 8 to 15 (depending on your units)

---

## 4.3 Collision Detection (Simple)

### AABB (Axis-Aligned Bounding Box)
Two rectangles/boxes collide if they overlap on all axes.

### Circle / Sphere
Two circles collide if the distance between centers ≤ sum of radii.

These are the most common broad-phase checks for 2D games.

---

## 4.4 Collision Response

When a collision is detected you usually need to:

1. Separate the objects (push them apart)
2. Adjust velocity (stop, bounce, slide)

Simple ground collision:
```text
if (player collides with ground)
{
    position.y = ground.top
    velocity.y = 0
    isGrounded = true
}
```

---

## 4.5 Raycasting (Concept)

A raycast shoots an invisible line and tells you what it hits first.

Common uses:
- Ground checks
- Line of sight
- Shooting
- Wall detection

---

## Key Takeaways
- Always multiply movement by deltaTime
- Separate collision detection from collision response
- Start with AABB or circles — they are simple and fast
- Grounded checks are essential for platformers

---

## Practice Ideas
1. Move a character left/right with acceleration and friction.
2. Implement gravity + jump.
3. Write AABB overlap test in pseudo-code.
4. Design a simple grounded check using a ray or box.

---

## Next Step
→ [05. Time & Timing Systems](05-time-and-timing-systems.md)
