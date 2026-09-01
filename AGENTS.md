# AGENTS.md — Hello-Wine-AppImage

## What this is
Demonstration project packaging a Windows `.exe` program inside a self-contained Linux AppImage, using a portable Wine AppImage for the Windows runtime.

## Stack
- Portable Wine (wine-stable AppImage)
- AppImage tooling (appimagetool)
- GitHub Actions (linux.yml)

## Build
```bash
chmod +x appimagetool-x86_64.AppImage
ARCH=x86_64 ./appimagetool-x86_64.AppImage hello.AppDir/
```

## Run
```bash
chmod +x Hello-x86_64.AppImage
./Hello-x86_64.AppImage
```

## Structure
- `hello.AppDir/` — AppImage staging directory (app + Wine prefix)
- `hello.AppDir/prefix/` — pre-built Wine prefix
- `appimagetool-x86_64.AppImage` — build tool
- `.github/workflows/linux.yml` — CI build/release workflow

## Conventions
- No comments in code unless asked.
- Verify: build via `appimagetool`, or run workflow with `act`.