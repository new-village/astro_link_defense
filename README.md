# Astro Link Defense

Astro Link Defense is a modular tower-defense strategy game built with Flutter.  
Your mission: Protect the space station from incoming meteors using strategically connected laser modules.

## Features (MVP)

- Top screen with START button
- Drag-and-drop module setup screen with a central core
- Defense screen with meteor animations and auto-firing lasers
- Result screen on success or failure
- Built for web, with future plans for Android/iOS

## Tech Stack

- **Flutter (Web-first)**
- **Standard Widgets & Animation Framework**
- Future support for **Flame** game engine

## Folder Structure

```
lib/
├── main.dart                # エントリーポイント
├── app.dart                 # MaterialApp定義、ルーティングなど
├── config/                  # 定数、設定ファイルなど
│   └── game_config.dart
├── core/                    # 基本ユーティリティ（共通処理、定義）
│   ├── constants.dart
│   └── enums.dart
├── models/                  # データモデル
│   ├── module.dart          # モジュール（レーザー、パワー等）
│   └── meteor.dart          # 隕石
├── providers/               # 状態管理（RiverpodやChangeNotifierなど）
│   └── game_state.dart
├── services/                # ロジック層（当たり判定、スコア計算など）
│   └── game_engine.dart
├── ui/                      # UI関連
│   ├── screens/             # 各画面
│   │   ├── start_screen.dart
│   │   ├── module_setup_screen.dart
│   │   ├── defense_screen.dart
│   │   └── result_screen.dart
│   ├── widgets/             # 再利用可能なWidget
│   │   ├── module_tile.dart
│   │   ├── core_module_widget.dart
│   │   └── laser_effect.dart
│   └── theme/               # カラー、フォント、スタイル
│       └── app_theme.dart
└── flame_game/              # 将来的にFlameを導入する場合のための空間
    └── astro_game.dart      # Flame用のゲーム本体（後で追加）
```

## Development

```bash
### 1. Install dependencies
flutter pub get
### 2. Run the web app
flutter run -d chrome
### 3. Build for production
flutter build web
```

## Roadmap
* Add audio effects (laser, explosion)
* Introduce scoring and leveling system
* Transition animation logic to Flame
* Release on Android and iOS
* Implement multi-stage campaign mode

## License
This project is licensed under the MIT License.