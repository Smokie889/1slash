# Movement Specification (v0.2)

---

## Core Principle

Movement is controlled stepping, not free running.

Distance is the primary gameplay variable.

Precision stopping is more important than peak movement speed.

---

## Facing & Axis

- Characters always face each other
- No cross-over
- No side switching
- 1D movement only

Forward = toward opponent  
Backward = away from opponent

---

## Distance Layers

### Point Blank
0 ~ 55px  
- immediate threat zone  
- high lethality  
- fast resolution

---

### Edge Range
56 ~ 90px  
- Light may hit or whiff  
- main close-range interaction layer  
- shimmy / delay / parry bait happen here

---

### Neutral Pressure Range
91 ~ 150px  
- Medium charge pressure zone

---

### Far
151px+  
- low immediate threat

---

## Base Movement

Forward speed:
120 px/s

Backward speed:
95 px/s

---

## Acceleration Model

Acceleration:
850 px/s²

Deceleration:
1300 px/s²

Stop Threshold:
|velocity| < 12 px/s → snap to 0

Design intent:
- responsive start
- very controllable stop
- supports edge-range precision

---

## Collision Rule

- Characters cannot overlap
- Minimum separation: 20px
- Movement clamps at boundary

No pushing, no sliding through opponent

---

## Charge Movement Modifiers

Medium Hold:
- speed multiplier: 0.55

Heavy Hold:
- speed multiplier: 0.35

---

## Feint Movement

Medium Feint:
- speed: 0.85 × base
- lockout: 120ms

Heavy Feint:
- speed: 0.75 × base
- lockout: 150ms

During Feint Lockout:
- movement allowed
- attack disabled
- parry disabled
- dash disabled

---

# Dash System

## Purpose

Dash is a re-engage tool.

Dash does not guarantee contact.  
Dash does not guarantee damage.

---

## Activation

Dash is only available after:
- successful parry vs Heavy
- pushback state occurs
- player presses forward

---

## Dash Kinematics

Startup:
40ms

Travel:
90ms

Max Distance:
88px

---

## Dash Termination Conditions

Dash ends when any of the following occurs:

1. Player presses attack confirm (Brake)
2. Dash reaches max distance
3. Distance reaches minimum separation boundary

---

## Dash Brake (Critical Rule)

During Dash:

Attack confirm input acts as a Brake.

Brake behavior:
- immediately stops or sharply reduces movement
- does NOT create an attack hitbox

This is NOT a Light Attack.

---

## Post-Brake Behavior

After braking:

- player enters a short action lockout (~80–110ms)
- movement allowed (reduced)
- attack disabled during lockout
- parry disabled during lockout
- dash disabled

To perform a real Light Attack:
- player must press attack confirm again AFTER lockout

---

## Design Intent (Brake)

- allow mid-dash spacing correction
- allow stopping at Edge Range
- prevent dash from becoming a guaranteed attack tool

---

## Contact Handling During Dash

If during Dash:

distance ≤ minimum separation

Then:
- dash immediately terminates
- no further forward movement is applied

Player enters close-range interaction state.

---

## Important Rule

Dash does NOT push inside the opponent.

Dash delivers the player to the fight,
not into overlap.

---

## Dash Outcome by Distance

Dash result depends on spacing at Heavy parry moment.

### Close Parry
- pushback small
- dash may enter Point Blank

---

### Mid Parry
- pushback medium
- dash lands in Edge Range

---

### Far Parry
- pushback large
- dash ends near Neutral-edge

---

## Pushback System

Triggered on Heavy parry

Distances:

Close:
58px

Mid:
96px

Far:
138px

---

## Movement Precision

Players must be able to:

- stop exactly at Edge Range
- adjust distance with small taps
- avoid overshooting into Point Blank

---

## Micro Movement

Short tap (80–100ms input):
~8–14px displacement

Supports:
- shimmy
- spacing adjustment
- baiting

---

## Combat Alignment

Movement must align with combat timing:

- Light startup (~90ms) must be readable vs movement
- stopping must allow immediate attack
- dash landing must match distance layer expectations

---

## Design Philosophy

Movement creates decisions.

Dash starts the next interaction.  
Brake decides where the interaction begins.

Distance → Decision → Resolution

The system must feel:
- deliberate
- readable
- controllable