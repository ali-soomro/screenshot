# screenshot — Cutefish Screenshot Tool

## Purpose
Screenshot utility for CutefishOS with capture and save functionality.

## Build
```bash
cmake -B build -DCMAKE_INSTALL_PREFIX=/usr && cmake --build build && sudo cmake --install build
```

## Dependencies
- Qt6 (Core, DBus, Gui, Widgets, Quick, LinguistTools)

## Structure
- `src/main.cpp` — entry point
- `src/screenshotview.cpp/h` — screenshot viewing/handling
- `qml/main.qml`, `qml/ImageButton.qml` — QML UI

## Install Targets
- Binary → `${CMAKE_INSTALL_BINDIR}`
- Desktop file → `/usr/share/applications/`
- Translations → `/usr/share/cutefish-screenshot/translations/`

## Qt5→Qt6 Migration Notes
- Qt5 → Qt6
- `Qt::X11BypassWindowManagerHint` guarded with `if (platformName == "xcb")`
- Added explicit `#include <QFile>` (no longer pulled transitively in Qt6)

## Status
✅ Ported, built, installed, pushed (github.com/ali-soomro)
