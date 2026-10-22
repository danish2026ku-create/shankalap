# Contributing to Sankalp JEE

Thank you for your interest in contributing! 🪔

## Development Setup

1. Install Android Studio (latest stable)
2. Clone this repository
3. Open the project in Android Studio
4. Sync Gradle (File → Sync Project with Gradle Files)
5. Run on an emulator or physical device (API 26+)

## Build Phases

Follow the build order in the spec:

1. ✅ Skeleton + theme tokens + icon + splash (Phase 1) — **DONE**
2. ✅ Data layer: Room, DataStore, seed syllabus, repositories, Hilt (Phase 2) — **DONE**
3. ✅ Navigation + shared components + Home (Phase 3) — **DONE**
4. ✅ Focus timer (Phase 4) — **DONE**
5. 🔄 App blocker + notification blocker + permissions (Phase 5) — **In Progress**
6. 🔄 Music player + soundscapes (Phase 6) — **In Progress**
7. 🔄 All ten themes + live backgrounds (Phase 7) — **In Progress**
8. 📋 Planner + syllabus (Phase 8) — **TODO**
9. 📋 Practice + analysis (Phase 9) — **TODO**
10. 📋 Revision + SM-2 + formula vault (Phase 10) — **TODO**
11. 📋 Widgets + tile + notifications + onboarding + backup (Phase 11) — **TODO**
12. 📋 Release build, R8, GitHub Actions (Phase 12) — **TODO**

## Code Style

- Kotlin coding conventions
- Compose UI patterns (single StateFlow per ViewModel)
- Domain layer: pure Kotlin, no Android imports
- All UI strings in `strings.xml` (no hardcoding)
- 4/8pt spacing grid
- Material 3 design tokens

## Architecture

```
ui → domain → data
```

**Strict one-way dependency.** UI never touches the database directly.

## Testing

- Unit tests for domain use cases (SM-2, Weakness Radar, Rank Estimator)
- Integration tests for repositories
- UI tests with Compose Test (future)

## License

This is a personal project for JEE aspirants. Free to use and modify.

---

**Resolve to Rise.** 🪔
