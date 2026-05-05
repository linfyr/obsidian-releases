# Mobile Version Desktop Widget Analysis

## Overview

This document analyzes whether the Obsidian mobile application (iOS and Android) has
**home-screen / desktop widget** support that allows users to quickly view and edit notes
without opening the full app.

---

## Conclusion

> **The core Obsidian mobile app does not currently ship native home-screen widget support
> for either Android or iOS.**

There is no built-in mechanism for placing an Obsidian widget on the Android home screen
or in the iOS Today/Home Screen widget gallery that surfaces note content directly.

---

## Available Community Plugins (Partial Solutions)

The plugins below are the closest approximations available in the community plugin
registry. They are grouped by what kind of "quick access" they provide.

### Mobile Toolbar Enhancements (in-app)

| Plugin ID | Plugin Name | Description |
|-----------|-------------|-------------|
| `cmdr` | Commander | Customize workspace, create macros, and supercharge the mobile toolbar. |
| `double-row-toolbar` | Double Row Toolbar | Adds a second row to the toolbar on mobile devices for more quick-access buttons. |
| `gay-toolbar` | Gay Toolbar | Colorful, customizable toolbar designed for mobile. |

### Mobile Navigation & Sidebar (in-app)

| Plugin ID | Plugin Name | Description |
|-----------|-------------|-------------|
| `mobile-sidebar-notes` | Mobile Sidebar Notes | Open notes and new tabs in the sidebar on the mobile app. |
| `cluster` | Cluster | Simplifies note clustering on mobile devices. |

### Quick Capture / Quick Note (desktop-focused, limited mobile benefit)

| Plugin ID | Plugin Name | Description |
|-----------|-------------|-------------|
| `quicknote` | Quick Note | Create a quick note in a floating window (desktop: right-click tray icon). |
| `tray` | Tray | Run Obsidian from the system tray with global quick-note access (desktop only). |
| `quickly` | Quickly | Navigate and create notes through OS shortcut keys (desktop). |

### iOS Shortcuts Bridge

| Plugin ID | Plugin Name | Description |
|-----------|-------------|-------------|
| `obsidian-shortcut-launcher` | Shortcut Launcher | Trigger commands in Apple's Shortcuts app from within Obsidian (iOS). By combining this with an iOS Shortcut widget, users can approximate a quick-capture widget on iOS. |

---

## Gap Analysis

| Capability | iOS | Android |
|------------|-----|---------|
| Native home-screen widget showing note content | ❌ Not available | ❌ Not available |
| Home-screen widget for quick note capture | ❌ Not available | ❌ Not available |
| Lock-screen widget / notification actions | ❌ Not available | ❌ Not available |
| In-app toolbar customization (requires app open) | ✅ Via `Commander` / `Double Row Toolbar` | ✅ Via `Commander` / `Double Row Toolbar` |
| iOS Shortcuts integration (requires Shortcuts app) | ⚠️ Partial via `Shortcut Launcher` | N/A |
| Quick note from outside the app | ❌ Not available | ❌ Not available |

---

## Recommendations

1. **iOS workaround** – Use the `Shortcut Launcher` plugin to create an iOS Shortcut that
   opens Obsidian and creates a new note. The shortcut can then be added as a home-screen
   icon or widget via the iOS Shortcuts widget.

2. **Android workaround** – Use Android's built-in app shortcut (long-press the Obsidian
   icon) if the app exposes shortcuts, or use a third-party launcher that supports URL
   schemes (e.g., `obsidian://new`) to create a quick-capture icon.

3. **Community plugin opportunity** – A dedicated community plugin could implement
   native home-screen widget support using each platform's plugin API:
   - **Android**: An Android app widget (`AppWidgetProvider`) could be bundled in a
     Capacitor/Cordova plugin, displaying the last-edited note and a "New note" button.
   - **iOS**: A WidgetKit extension could expose the same functionality for iOS 14+.

4. **Feature request** – If native widget support is important to you, file a feature
   request at the [Obsidian community forum](https://forum.obsidian.md) or vote on
   existing requests so the core team can prioritize it.

---

## Related Community Plugins (Stats Reference)

The download statistics for the most relevant plugins can be found in
[`community-plugin-stats.json`](./community-plugin-stats.json). The plugin IDs listed
above can be used to look up their adoption numbers and decide which partial solution
is most widely used.
