# Astro Link Defense - Architecture Overview

This document provides an overview of the software architecture for **Astro Link Defense**, a modular tower-defense game built using Flutter.

## Goals
- Keep initial implementation simple and maintainable
- Enable future transition to Flame for enhanced animations and performance
- Support expansion to Android and iOS platforms

---

## App Layers

### 1. **Presentation Layer (UI)**
- **Location:** `lib/ui/`
- **Responsibility:** Handles screen layouts, user interaction, animations
- **Widgets:**
  - `screens/`: Top screen, module setup, defense, result
  - `widgets/`: Reusable widgets (laser, module tile, core, etc.)
  - `theme/`: Centralized styling

### 2. **State Management**
- **Location:** `lib/providers/`
- **Pattern:** Initially `ChangeNotifier`, optionally migratable to `Riverpod`
- **GameState:** Holds game phase (start/setup/defend/result), module placements, game outcome, etc.

### 3. **Domain Layer (Models)**
- **Location:** `lib/models/`
- **Responsibility:** Define core game data structures
  - `Module`: Type (laser, power, etc.), position, connected directions
  - `Meteor`: Position, velocity, HP, size

### 4. **Logic Layer (Services)**
- **Location:** `lib/services/`
- **Game Engine (`game_engine.dart`)**
  - Advances game loop, handles collisions, laser-meteor hit detection
  - Evaluates win/loss conditions

### 5. **Configuration & Constants**
- **Location:** `lib/config/`, `lib/core/`
- `game_config.dart`: Game speed, meteor spawn rates, damage values
- `constants.dart`, `enums.dart`: Shared definitions (e.g., directions, module types)

---

## Game Flow

```text
StartScreen → ModuleSetupScreen → DefenseScreen → ResultScreen
```

Each screen is a separate widget managed by Flutter routing. Transitions occur via state changes triggered by user actions or game logic.

---

## Future Expansion: Flame Compatibility

> The current structure is designed to be compatible with the Flame engine for smoother and more efficient animations.

When ready:
- Replace defense animations with Flame’s `SpriteComponent`
- Move `game_engine.dart` logic into `astro_game.dart` under `lib/flame_game/`
- Use Flame’s collision system and component lifecycle

---

## Platform Targets

- ✅ Web-first (initial MVP)
- ⏳ Android (post-MVP)
- ⏳ iOS (after Android release)

---

## Summary
This architecture separates concerns clearly and scales well as the game evolves. Early development remains lightweight, while providing a path toward a fully-featured mobile game experience.
