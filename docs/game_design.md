# Astro Link Defense - Game Design Specification

This document outlines the gameplay mechanics, objectives, and module specifications for **Astro Link Defense**.

## Core Gameplay Loop

1. **Start Screen**  
   User presses START to begin mission.

2. **Module Setup Phase**  
   - A central core module is fixed on the grid.
   - Player drags and connects modules (e.g., Laser, Power, Splitter) from a limited palette.
   - Once ready, the player starts the defense phase.

3. **Defense Phase**  
   - Meteors fly toward the space station from the screen edge.
   - Modules automatically fire lasers based on their configuration.
   - Lasers intercept meteors in real-time.

4. **Result Phase**  
   - All meteors destroyed → Mission Cleared
   - Any meteor reaches the core → Game Over

---

## Grid System
- Grid size: 10x10
- Core module is placed at center (e.g., [5][5])
- Modules can only be placed on adjacent grid squares
- All modules must connect back to the core directly or indirectly

---

## Module Types

| Type         | Description                                           | Notes                                |
|--------------|-------------------------------------------------------|--------------------------------------|
| Core         | Central module, always present                       | Cannot be removed                    |
| Laser        | Fires a beam in one direction                        | Can be powered up                    |
| Power        | Boosts output of connected Laser modules             | Must be linked before Laser          |
| Splitter     | Sends power in two directions                        | Adds branching logic                 |
| Charger      | Increases fire rate of connected modules             | Stackable                            |
| Rotator      | Rotates connected Laser direction over time          | Advanced module (future)            |

---

## Meteor Types (MVP)

| Type     | HP   | Speed | Size  | Notes                       |
|----------|------|-------|-------|-----------------------------|
| Small    | 1    | Fast  | Tiny  | Easy to destroy             |
| Medium   | 2    | Medium| Normal| Standard threat             |
| Large    | 4    | Slow  | Big   | High damage if it hits     |

---

## Scoring & Progression (Future Update)
- Points awarded for destroying meteors
- Bonus for unused modules or overkill
- Score affects XP and unlocks new module types

---

## UI Summary

### Start Screen
- Game title
- Start button

### Module Setup Screen
- Central core on grid
- Draggable module palette
- [DEFEND] button to begin wave

### Defense Screen
- Animated meteor spawns
- Laser beams auto-fire
- Visual impact effects

### Result Screen
- Display result (Win/Lose)
- Meteor stats and accuracy
- Buttons: Retry / Next (future)

---

## Difficulty Scaling (Future)
- Increase meteor spawn rate and types per wave
- Limited module count or power cap
- Special challenge stages

---

## Summary
Astro Link Defense combines spatial puzzle elements with real-time tower defense mechanics. Strategic placement and module linking are key to survival.
