# Movement Specification (v0.1)

---

## Core Principle

Movement is controlled stepping, not free running.

Position control should feel deliberate and readable.
Distance is the primary spatial variable.

---

## Facing & Axis

- Characters always face each other.
- No cross-over. No side switching.
- 1D axis only (left / right).

Forward = toward opponent  
Backward = away from opponent

---

## Distance Units

All distances use a unified unit (px).

Suggested initial anchors:
- Light Range: ~80px
- Edge Range: 70px ~ 90px band
- Medium Pressure Range: ~140px
- Far Range: ~220px+

(All values are provisional and must be tuned together.)

---

## Base Movement

### Walk Speed

- Forward speed: 120 px/s
- Backward speed: 100 px/s

Design intent:
- Slight forward bias encourages engagement
- Backward is viable but not dominant

---

## Acceleration Model

Movement should not be instant.

### Acceleration
- accel: 900 px/s²

### Deceleration
- decel: 1100 px/s²

### Stop Threshold
- if |velocity| < 10 px/s → snap to 0

Design intent:
- Quick to start, slightly quicker to stop
- Enables precise micro-spacing (edge range play)

---

## Input Model

- Left / Right held → continuous movement
- No inertia carry after input release (fast decel)
- No diagonal / vertical movement

---

## Charge Movement Modifiers

### Medium Charge
- move speed multiplier: 0.55

### Heavy Charge
- move speed multiplier: 0.35

Design intent:
- Charge expresses commitment through reduced mobility
- Still allows repositioning (not a root)

---

## Feint Movement

During Feint Lockout:

### Medium Feint
- move speed: 0.85 × base

### Heavy Feint
- move speed: 0.75 × base

- movement allowed
- no attack / parry / dash

Design intent:
- reposition without offense
- maintain flow, avoid “freeze”

---

## Dash System (Re-engage Only)

Dash is only available after:
- successful parry vs Heavy
- pushback occurs

### Dash Input
- press forward again

---

### Dash Kinematics

- startup: 40ms (no movement)
- travel duration: 100ms
- total duration: ~140ms

### Dash Distance (base)
- 90px (provisional)

---

## Distance-Dependent Dash Outcome

Dash result depends on spacing at Heavy-parry moment.

### If parry at Close
- pushback: small
- dash → likely Point Blank

### If parry at Mid
- pushback: medium
- dash → Edge Range

### If parry at Far
- pushback: large
- dash → Neutral-edge (not guaranteed close)

Design rule:
Dash re-engages; it does not guarantee contact.

---

## Pushback System

Triggered on Heavy parry.

### Pushback Distance (tiered)

- Close: 60px
- Mid: 100px
- Far: 140px

(Values must be tuned against dash distance.)

### Pushback Feel

- short hit-stop (~40ms)
- smooth backward slide (80~120ms)
- no control during slide

---

## Micro-Spacing Window

Critical gameplay zone: Edge Range (~±10px around Light range)

Movement system must allow:
- small forward tap
- small backward tap
- quick stop

Design requirement:
- player must be able to “hover” at light boundary

---

## Collision Rule

- Characters cannot overlap
- Minimum separation maintained (e.g., 20px)
- Movement clamps at collision boundary

No pass-through allowed.

---

## Timing Alignment (Important)

Movement must align with combat timings:

- Light startup (~90ms) must be readable relative to walk speed
- Deceleration must allow stop → light without overshoot
- Dash arrival should place player near intended range tier

---

## Balance Rules

- Movement must not be faster than reaction readability
- Acceleration must not cause overshoot at Edge Range
- Backward movement must not invalidate pressure
- Charge slowdown must be meaningful but not crippling
- Dash must not collapse spacing layers

---

## Design Philosophy

Distance creates decisions.

Movement should enable:
- approach
- hesitation
- bait
- correction

Not:
- evasion spam
- constant drift
- unreadable jitter

The player should feel:
“I moved there on purpose.”