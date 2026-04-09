# Combat Timing Specification (v0.2)

---

## Core Principle

Light controls close combat.  
Medium controls neutral pressure.  
Heavy controls space and resets.

Feint is mobility without offensive rights.

The game should build toward the final decision.  
It should not always start at the decision.

---

## Combat Goal

1SLASH is a one-hit duel system.

The fight is structured as:
- pressure
- approach
- spacing reads
- final fast resolution

Point-blank exchanges should be decisive and dangerous.  
But the game should not collapse into constant blind guessing.

---

## Base Movement

- Movement axis: 1D (left / right)
- Base move speed: 100%

---

## Distance Layers

### 1. Point Blank
Very close range.

Properties:
- Light Attack is immediately threatening
- Exchanges resolve very quickly
- Highest risk / highest lethality zone

This is the final decision layer.

---

### 2. Edge Range
Boundary of Light Attack range.

Properties:
- Light may barely connect or barely miss
- Shimmy, delay, micro-walk, parry bait all matter
- This is the main close-range mindgame layer

This is where fast but readable close combat should happen.

---

### 3. Neutral Range
Outside immediate Light range.

Properties:
- Medium Charge is the main pressure tool
- Heavy Charge shapes space and commitment
- Movement and charge timing are dominant here

---

## Attack System

### 1. Light Attack (No Charge)

Triggered by pressing attack confirm without holding.

Role:
- close-range weapon
- fast interrupt
- spacing brake
- dash follow-up threat

Properties:
- fastest attack
- shortest range
- strong at Point Blank and Edge Range
- high risk if parried
- lower punishment on whiff than on parry

Timing:
- startup: 90ms
- active: 60ms
- whiff recovery: 190ms

On successful parry against Light:
- attacker enters Punishable State
- defender gains Punish Confirm Window
- defender must press attack confirm to convert the advantage into a hit

---

### 2. Medium Charge Attack

#### Charge Phase
- hold duration: 300ms ~ 649ms
- move speed during hold: 55%

Role:
- main neutral pressure tool
- forces decisions
- primary timing / spacing pressure layer

#### Confirmed Attack
- startup: 140ms
- active: 90ms
- whiff recovery: 280ms

On successful parry against Medium:
- attacker enters Punishable State
- defender gains Punish Confirm Window
- defender must press attack confirm to convert the advantage into a hit

---

### 3. Heavy Charge Attack

#### Charge Phase
- hold duration: 650ms+
- move speed during hold: 35%

Role:
- high-commitment pressure
- space control
- exchange rewriting tool

Heavy is not just a move.  
Heavy is a state with options.

#### Confirmed Attack
- startup: 170ms
- active: 100ms
- whiff recovery: 340ms

On successful parry against Heavy:
- no direct punish confirm
- triggers Pushback State
- defender gains positional initiative instead of automatic damage

---

## Parry System

### Input
- dedicated parry button

### Purpose
Parry is a commitment to a prediction.

Parry success should grant initiative, not automatic damage.

### Timing
- startup: 50ms
- active window: 120ms
- miss recovery: 300ms

---

## Parry Outcomes

### Parry vs Light
- attacker enters Punishable State
- defender gains Punish Confirm Window
- defender must press attack confirm to convert

### Parry vs Medium
- attacker enters Punishable State
- defender gains Punish Confirm Window
- defender must press attack confirm to convert

### Parry vs Heavy
- no direct punish confirm
- trigger Pushback State
- defender gains positional initiative

---

## Punishable State / Punish Confirm Window

This is not automatic counter damage.

When Light or Medium is successfully parried:
- attacker enters a punishable state
- defender receives a short conversion window
- defender must press attack confirm to secure the hit

Design intent:
- reward successful reads
- preserve player execution
- avoid automatic scripted outcomes

---

## Whiff vs Parry Penalty

Whiff and parry are fundamentally different outcomes.

### Whiff
Represents failed spacing or timing.
- should hurt
- should be punishable
- should not always be fatal

### Parried
Represents a successful counter-read by the opponent.
- should hurt significantly more than whiff
- should grant a clearly stronger advantage

System rule:
- whiff recovery and on-parry punishment must always remain distinct

Design principle:
Missing should hurt.  
Getting read should hurt more.

---

## Feint System

Releasing charge without confirming an attack triggers Feint.

Feint is not a full recovery state.  
Feint is a movement-allowed action lockout state.

---

## Feint Lockout

During Feint Lockout:
- movement: allowed
- attack: disabled
- parry: disabled
- dash: disabled
- re-hold: disabled

### Medium Feint
- lockout duration: 120ms
- move speed during lockout: 85%

### Heavy Feint
- lockout duration: 150ms
- move speed during lockout: 75%

Design intent:
- allow repositioning
- prevent immediate re-attack abuse
- preserve neutral flow

---

## Heavy Conversion Rule

While in Heavy Charge, player may convert into Light Attack.

Purpose:
- prevent free walk-in pressure against Heavy
- give Heavy state a minimal reactive defense option
- preserve close-range threat without making Heavy safe

### Conversion Timing
- heavy-to-light conversion delay: 20ms ~ 40ms
- resulting converted Light startup target: ~70ms

This value is provisional and should be tested.

---

## Pushback State

Triggered when:
- Heavy Attack is successfully parried

Purpose:
- deny direct punish on Heavy
- create a new positional exchange instead
- lead into re-engage pressure

---

## Pushback Recovery

Base recovery targets after Heavy is parried:
- Heavy attacker recovery: 320ms
- Parry success recovery: 180ms

Result:
- parry-success player gains initiative window
- but not automatic guaranteed damage

---

## Dash System

Dash is not freely usable.

Dash can only be triggered when:
- player successfully parries a Heavy Attack
- Pushback State occurs
- player presses forward again toward the opponent

Purpose:
- re-engage the fight
- begin a new decision space
- not directly end the exchange

Design rule:
Dash grants initiative, not guaranteed priority.

Dash should start the next fight, not automatically end it.

### Dash Timing
- startup: 40ms
- travel: 100ms
- total: ~140ms

These values are provisional.

---

## Dash Outcome by Original Distance

Dash result should depend on the original spacing when Heavy was parried.

This is a critical system rule.

### If Heavy is parried at close distance
- pushback is shorter
- dash may re-enter Point Blank directly

### If Heavy is parried at mid distance
- pushback is moderate
- dash usually ends in Edge Range

### If Heavy is parried at far distance
- pushback is larger
- dash may only return to Neutral-edge distance
- direct close combat is not guaranteed

Design intent:
- Dash should not always force immediate point-blank guessing
- spacing before the parry should matter
- re-engage should sometimes create direct lethal pressure, and sometimes only partial advantage

---

## Close-Range Interaction Model

Close-range combat is not one single layer.

It has two layers:

### Layer A: Edge Range
Main readable close combat layer.

Tools:
- Light Attack
- Parry
- Shimmy
- delay
- micro-walk
- spacing adjustment

This layer should feel:
- fast
- tense
- readable
- skill-based

### Layer B: Point Blank
Final decision layer.

Tools:
- Light Attack
- Parry

This layer should feel:
- explosive
- highly lethal
- fast resolving

Point Blank may become a near-guessing moment, and that is acceptable.  
But the system should not force every re-engage directly into Point Blank.

---

## Shimmy Definition

Shimmy is not only a defense against Light.

Shimmy is:
- a short delay
- a small reposition
- a bait action
- a timing trap

Purpose:
- make immediate retaliation fail
- bait Parry
- make Light whiff or mistime near Edge Range
- create a better confirm opportunity

Shimmy belongs mainly to Edge Range, not strict Point Blank.

---

## Visual Readability Principles

Reaction readability must come from stance clarity, not visual complexity.

The game does not need complex animation to be readable.  
It needs clear combat cues.

### Required readability signals

#### Medium Hold
- clearly distinguishable charged stance
- readable as a real threat state

#### Heavy Hold
- more committed and more visually severe than Medium
- visibly slower and more dangerous

#### Parry
- must have a clear startup cue
- should be quickly readable by posture / flash / direction change

#### Pushback
- should feel forceful and unmistakable
- spacing change must be obvious

Design principle:
Fast pacing must come from fast resolution,  
not unreadable startup.

---

## Full Combat Flow

Neutral →

Charge pressure →

Attack or Feint →

Parry →

If Light / Medium parried:
- Punishable State
- Punish Confirm Window

If Heavy parried:
- Pushback State
- Dash opportunity
- re-entry by spacing tier

Then:

- Edge Range interaction
or
- Point Blank final exchange

Then:
- resolution
- death
or
- reset to neutral

---

## Balance Rules

- Heavy must remain risky
- Parry must remain precise
- Feint must preserve movement but remove immediate offense
- Light whiff must be safer than Light parried
- Dash must grant initiative, not guaranteed first hit
- Original spacing before Heavy parry must matter
- Point Blank can be decisive
- Edge Range must remain the main readable close-range layer

---

## Design Philosophy

Parry does not end the fight.  
Parry creates the next fight.

Dash should bring players into a decision space,  
not directly into a decision result.

The game should feel fast because decisions resolve quickly,  
not because actions are unreadably fast.