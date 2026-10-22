# 🪔 Sankalp JEE

> **"Sankalp" means resolve — the unwavering determination to rise.**

Free, offline-first Android super app for JEE (Main + Advanced) aspirants.

**No internet. No distractions. Pure resolve.**

---

## ✨ Features

### 🎯 Focus Timer
- Customizable Pomodoro-style sessions (25m, 35m, 52m, 60m, 90m)
- 4 focus modes: Gentle → Standard → Strict → Lockdown
- Persistent foreground service with live countdown notification

### 🛡️ App Blocker & Notification Guard
- Accessibility Service blocks selected apps during focus
- Notification Listener silences distracting notifications
- Reels/Shorts detection via view-id matching
- Configurable block list per session

### 📋 Study Planner
- Daily task management with subject tags
- Syllabus tracker — 62 chapters across Physics, Chemistry, Mathematics
- Weightage tiers (High/Medium/Low) for priority planning
- Backlog tracker for overdue tasks

### 📝 Practice & Analysis
- Mock test logging with per-subject breakdown
- Error Book — categorize mistakes (Conceptual, Calculation, Silly, etc.)
- Weakness Radar — composite scoring across errors, mastery gaps, weightage
- Rank Estimator — rolling average with trend detection

### 🧠 Revision System
- SM-2 spaced repetition algorithm
- Flashcard creation and review
- Formula Vault for quick-reference formulas
- Quick Notes system

### 🎵 Study Music
- 12 bundled ambient soundscapes (rain, forest, binaural, etc.)
- Mini player with loop support
- MediaStore integration for custom audio

### 🎨 10 Themes + Live Backgrounds
| Theme | Background |
|---|---|
| Midnight Library | Drifting starfield |
| Temple Dawn | Rising warm gradient |
| Monsoon Study | Falling rain streaks |
| Kesar | Golden aurora |
| Neelkanth | Deep blue aurora |
| Forest Ashram | Leaf-shadow drift |
| Paper & Ink | Subtle paper grain |
| Aurora Nights | Flowing aurora ribbons |
| Copper Dusk | Warm haze |
| Emerald Focus | Gentle emerald pulse |

Auto mode: bright palettes before 17:00, darker after.

### 📊 Widgets
- Focus Timer widget
- Today's Plan widget
- Study Streak widget (🔥)
- Revision Due widget

### ⚡ Quick Settings Tile
- One-tap focus mode toggle from notification shade

### 🔥 Streak System
- Daily study streak tracking
- Streak Guard worker resets on missed days
- Longest streak record

---

## 🏗️ Architecture

```
ui → domain → data
```

**Three layers, one direction of dependency.**

- **ui/** — Compose screens, ViewModels (StateFlow), theme, navigation
- **domain/** — Pure Kotlin: models, SM-2 engine, weakness radar, rank estimator
- **data/** — Room database, DataStore preferences, repositories
- **service/** — AccessibilityService, NotificationListener, Workers
- **di/** — Hilt modules

### Tech Stack
- Kotlin + Jetpack Compose (Material 3)
- Room (SQLite) + DataStore
- Hilt (Dependency Injection)
- WorkManager (background workers)
- Glance (App Widgets)
- Media3 (Music playback)
- No network — zero INTERNET permission

---

## 📂 Project Structure

```
sankalp-jee/
├── app/src/main/
│   ├── java/com/sankalp/jee/
│   │   ├── SankalpApp.kt          (Application + Hilt)
│   │   ├── MainActivity.kt        (Single-activity NavHost)
│   │   ├── di/                    (AppModule, DatabaseModule, RepositoryModule)
│   │   ├── domain/
│   │   │   ├── model/             (13 domain models)
│   │   │   └── usecase/           (SM-2, WeaknessRadar, RankEstimator, etc.)
│   │   ├── data/
│   │   │   ├── local/             (Room DB, DAO, Entities, SeedData)
│   │   │   ├── prefs/             (DataStore preferences)
│   │   │   ├── music/             (Soundscape catalog, MediaStore)
│   │   │   └── rules/             (Reels detection rules)
│   │   ├── service/               (Guardian, Notification Guard, Focus Service, Workers)
│   │   ├── widget/                (4 Glance widgets)
│   │   ├── tile/                  (Quick Settings tile)
│   │   └── ui/
│   │       ├── theme/             (10 themes, live backgrounds, typography)
│   │       ├── nav/               (Routes, BottomBar, NavHost)
│   │       ├── components/        (Card, RingMeter, Confetti, etc.)
│   │       └── screens/           (Home, Focus, Planner, Practice, Revision, Music, Settings)
│   └── res/                       (Strings, Colors, Drawables, Widget layouts)
├── .github/workflows/             (CI: APK build)
├── gradle/libs.versions.toml      (Version catalog)
└── build.gradle.kts               (Root build config)
```

---

## 📊 Stats

| Metric | Count |
|---|---|
| Total files | 116 |
| Kotlin source files | 84 |
| XML resource files | 24 |
| Lines of code | ~7,800+ |
| Domain models | 13 |
| Use cases | 5 |
| Room entities | 7 |
| Themes | 10 (+ Auto) |
| Live backgrounds | 10 |
| JEE chapters seeded | 62 |
| Soundscapes | 12 |

---

## 🚀 Build

```bash
# Clone and build
cd sankalp-jee
./gradlew assembleDebug

# APK output
ls app/build/outputs/apk/debug/
```

### CI/CD
GitHub Actions builds APK on every push to `main` and `develop`.

---

## 📱 Screens

- **Home** — Greeting, streak, today's focus, subject progress, quick actions
- **Focus** — Timer ring, mode selector, subject tag, duration picker
- **Planner** — Today's tasks, syllabus tracker, backlog
- **Practice** — Mock test log, error book, weakness radar, rank estimation
- **Revision** — SM-2 flashcards, formula vault, notes
- **Music** — Soundscapes browser, mini player
- **Settings** — Theme picker, backup/restore, about
- **Onboarding** — 5-step flow (welcome, exam date, subjects, theme, permissions)

---

## 🎨 Design System

- **Font**: Manrope with tabular numbers
- **Grid**: 4/8pt spacing system
- **Motion**: Springs (bouncy 380/18, gentle 220/24), cubic-bezier easings
- **Reduced motion**: Respects system accessibility setting

---

*Built with resolve. 🪔*
