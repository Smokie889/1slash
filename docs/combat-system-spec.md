# Combat System Specification

"If your system already has a stable triangle,
do not add a fourth node."

---

## 🎯 Core Concept

1SLASH is a deterministic 1v1 duel system focused on timing, pressure, and decision-making.

The system is built around:
- Minimal inputs
- High-risk commitments
- Psychological interaction

---

## 🎮 Player Actions

- Move Left / Right
- Hold (Charge)
- Confirm Attack
- Parry
- Dash (conditional)

---

## ⚔️ Attack System

### Light Attack
- Fast execution
- Low commitment
- Punishable by parry
- No pushback interaction

---

### Heavy Attack (Charge-based)

Charge duration determines attack strength.

Properties:
- Increased impact with longer charge
- Cannot defend effectively while charging
- On parry:
  → Triggers pushback (no direct punish)

---

## 🛡️ Parry System

### Parry Window
- Short active timing window
- Requires precise timing

---

### Outcomes

#### vs Light Attack
→ Attacker enters stun  
→ Guaranteed punish

#### vs Heavy Attack
→ No stun  
→ Trigger pushback  
→ Transition to advantage state

---

## 💥 Pushback System

Triggered when:
- Heavy attack is parried

Effects:
- Both players are pushed apart
- Distance increases
- No immediate hit advantage

---

## ⚡ Advantage State (Post-Pushback)

Parry-success player gains:

- Shorter recovery
- First actionable window

Heavy attacker:
- Longer recovery

Result:
→ Parry player can dash forward first

---

## 🏃 Dash System

Dash is NOT freely usable.

### Conditions:
- Only available after parry success + pushback
- Triggered by pressing forward again

### Purpose:
- Re-engage opponent
- Enter close-range mindgame

---

## 🔁 Close-Range Mindgame (Core Triangle)

After dash-in:

### Options:

- Light Attack
- Parry
- Shimmy (delay / bait / no immediate action)

---

### Interaction Loop

Light → beats Shimmy  
Parry → beats Light  
Shimmy → beats Parry  

---

## 🧠 System Principle

The system is intentionally constrained.

There is no:
- Throw system
- Additional counter mechanics

Reason:
Maintaining a stable interaction triangle is critical.

---

## ⚖️ Balance Rules

- Heavy attack must carry risk (reduced mobility / vulnerability)
- Parry must require precision (tight timing window)
- Dash must not dominate neutral (restricted usage)

---

## 🔁 Full Combat Loop

Neutral →

Hold (pressure) →

Attack / Feint →

Parry →

Pushback →

Dash (advantage player) →

Close-range mindgame →

Resolution →

Reset

---

## 🧠 Design Philosophy

- Parry does not end the fight  
  → It creates the next fight  

- Every action is a commitment  

- Depth comes from interaction, not complexity  

---