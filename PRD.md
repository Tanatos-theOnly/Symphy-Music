# Symphy Music - Product Requirements & Execution Roadmap (Monster Mode)

## Project Vision
Transform the reference music streaming client (SimpMusic) into **Symphy music** with high-performance **Liquid Glassmorphism UI** powered by the AGSL shader engine from **PrismalAGSL**.

---

## High-Level Architecture
1. **Core Streaming & Engine**: Derived from SimpMusic Compose Multiplatform Clean Architecture (KMP, Media3 ExoPlayer, YouTube Music scrapers, Room, Koin).
2. **Liquid Glass UI Engine**: Integrated from PrismalAGSL (Android 13+ AGSL RuntimeShader with RenderEffect / Frost fallbacks, Spring physics, Haptics, Specular highlights, Edge lens refraction).
3. **Rebranding & Decoupling**: Rename to "Symphy music", replace author references and links, disable anti-fork/unofficial build lockouts, and connect GitHub update checker to the Symphy music repository.

---

## Phase 1: Reconnaissance & Interactive Architecture Alignment (CURRENT)
- [x] Analyze SimpMusic codebase (architecture, anti-fork check, author credits, update mechanism).
- [x] Analyze PrismalAGSL shader architecture (AGSL shaders, modifiers, bottom tabs dock, sliders).
- [ ] Align with user on author credentials, GitHub repo, package ID, and glass styling customizations via interactive UI.

## Phase 2: Workspace Setup & Clean Foundation
- [ ] Structure the root project directory (port SimpMusic source into workspace root).
- [ ] Integrate Prismal AGSL library as a subproject module `:prismal` or embedded components.
- [ ] Configure `settings.gradle.kts` and dependencies to link `:prismal` with `:composeApp` and `:androidApp`.

## Phase 3: Rebranding & Author Credit Overhaul
- [ ] Change application name to "Symphy music" across all resources (`app_name.xml`, manifests, desktop configs).
- [ ] Replace author credits, URLs, developer screens, donation links, and copyright notices in `CreditScreen.kt`, strings, and legal MDs.
- [ ] Neutralize / adapt `UnofficialBuildScreen` & `Config.OFFICIAL_PACKAGE_NAMES` to prevent lockout.
- [ ] Repoint GitHub release update check (`checkForGithubReleaseUpdate`) to the new repository endpoint.

## Phase 4: Liquid Glass UI Transformation (PrismalAGSL)
- [ ] Wrap root container in `PrismalBackdrop` for real-time sampling.
- [ ] Implement Liquid Glass Dock (`PrismalGlassBottomTabs`) with draggable selection pill and spring motion.
- [ ] Implement Liquid Glass Sliders (`PrismalGlassSlider`) for mini-player seekbar, full player progress, and volume.
- [ ] Apply liquid glass surfaces (`PrismalGlassSurface` / `drawPrismalGlass`) to top app bars, dialogs, and menus.
- [ ] Verify haptics, spring animations, and fallback tiers (Liquid API 33+, Standard API 31-32, Legacy API 25-30, JVM Desktop).

## Phase 5: Verification, CodeRabbit Quality Gate & Polish
- [ ] Run Gravitas executable verification & syntax validation.
- [ ] Run CodeRabbit review audit on modified diffs.
- [ ] Final end-to-end verification report.
