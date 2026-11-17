# Symphy Music - Product Requirements & Execution Roadmap (Monster Mode)

## Project Vision
Transform the reference music streaming client (SimpMusic) into **Symphy music** with high-performance **Liquid Glassmorphism UI** powered by the AGSL shader engine from **PrismalAGSL**.

---

## High-Level Architecture
1. **Core Streaming & Engine**: Derived from SimpMusic Compose Multiplatform Clean Architecture (KMP, Media3 ExoPlayer, YouTube Music scrapers, Room, Koin).
2. **Liquid Glass UI Engine**: Integrated from PrismalAGSL (Android 13+ AGSL RuntimeShader with RenderEffect / Frost fallbacks, Spring physics, Haptics, Specular highlights, Edge lens refraction).
3. **Rebranding & Decoupling**: Rename to "Symphy music", replace author references and links, disable anti-fork/unofficial build lockouts, and connect GitHub update checker to the Symphy music repository.

---

## Phase 1: Reconnaissance & Interactive Architecture Alignment (COMPLETED)
- [x] Analyze SimpMusic codebase (architecture, anti-fork check, author credits, update mechanism).
- [x] Analyze PrismalAGSL shader architecture (AGSL shaders, modifiers, bottom tabs dock, sliders).
- [x] Align with user on author credentials, GitHub repo, package ID, and glass styling customizations via interactive UI.

## Phase 2: Workspace Setup & Clean Foundation (COMPLETED)
- [x] Structure the root project directory (port SimpMusic source into workspace root).
- [x] Integrate Prismal AGSL library as a subproject module `:prismal` or embedded components.
- [x] Configure `settings.gradle.kts` and dependencies to link `:prismal` with `:composeApp` and `:androidApp`.

## Phase 3: Rebranding & Author Credit Overhaul (COMPLETED)
- [x] Change application name to "Symphy music" across all resources (`app_name.xml`, manifests, desktop configs).
- [x] Replace author credits, URLs, developer screens, donation links, and copyright notices in `CreditScreen.kt`, strings, and legal MDs.
- [x] Neutralize / adapt `UnofficialBuildScreen` & `Config.OFFICIAL_PACKAGE_NAMES` to prevent lockout.
- [x] Repoint GitHub release update check (`checkForGithubReleaseUpdate`) to the new repository endpoint.

## Phase 4: Liquid Glass UI Transformation (PrismalAGSL) (COMPLETED & ACTIVE)
- [x] Wrap root container in `PrismalBackdrop` and live sampling layers.
- [x] Implement Liquid Glass Dock (`PrismalGlassBottomTabs` / `LiquidGlassTabBar`) with draggable selection pill and spring motion.
- [x] Implement Liquid Glass Sliders (`AppleMusicThinSlider` / `PrismalGlassSlider`) for player seekbar and volume.
- [x] Enable Liquid Glass by default out-of-the-box (`DataStoreManagerImpl.kt`, `SettingsViewModel.kt`, `App.kt`).

## Phase 5: Verification, CodeRabbit Quality Gate & Polish (COMPLETED)
- [x] Run Gravitas executable verification & full Android compilation suite (`:androidApp:assembleDebug`).
- [x] Verified generated APK packages: Universal, ARM64, x86_64, ARMeabi-v7a.
- [x] Code integrity, liquid glass shader linking, and clean rebranding confirmed.
