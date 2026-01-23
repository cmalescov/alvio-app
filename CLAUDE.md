# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Alvio is a React Native mobile app built with Expo 54, React 19, and TypeScript. It uses file-based routing with Expo Router and targets iOS, Android, and web platforms.

## Development Commands

```bash
npm start            # Start Expo dev server
npm run ios          # Run on iOS simulator
npm run android      # Run on Android emulator
npm run web          # Run in browser
npm run lint         # Run ESLint
npm run reset-project # Move starter code to app-example and reset app/
```

## Architecture

### Routing (Expo Router)
- `app/` - Active source code with file-based routing
- `app/_layout.tsx` - Root layout (Stack navigation)
- Route files map to URLs: `app/index.tsx` → `/`, `app/settings.tsx` → `/settings`

### Reference Code
- `app-example/` - Template patterns for components, hooks, themes, and navigation (moved here by reset-project script)

### Platform-Specific Code
Use file suffixes for platform-specific implementations:
- `.ios.ts` / `.android.ts` / `.web.ts`
- Example: `use-color-scheme.ts` (native) vs `use-color-scheme.web.ts` (web)

### Path Aliases
- `@/*` maps to project root (configured in tsconfig.json)

## Build Configuration

- **EAS Build Profiles** (eas.json):
  - `development` - Dev client build for devices
  - `development-simulator` - Dev client for iOS simulator
  - `preview` - Internal testing builds
  - `production` - App store release builds

- **Enabled Experiments** (app.json):
  - New Architecture (`newArchEnabled: true`)
  - TypedRoutes
  - React Compiler

## Key Technologies

| Purpose | Technology |
|---------|-----------|
| UI | React 19.1, React Native 0.81 |
| Platform | Expo 54.0 |
| Routing | Expo Router 6.0 |
| Animations | React Native Reanimated 4.1 |
| Gestures | React Native Gesture Handler 2.28 |