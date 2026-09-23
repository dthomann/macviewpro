# Changelog

All notable user-facing changes are listed here. Dates are release dates (local).

## [1.0.3] — 2026-09-23

### Added

- Paste into the current image places the clipboard at the mouse pointer (original size). Drag to move, Shift+corner to scale proportionally, click outside or Return to accept, Esc to cancel
- Paste into an empty window opens the clipboard there; closing prompts to Save As until you save

### Fixed

- Rename dialog widens for long filenames (including the extension) and scrolls horizontally so nothing is clipped
- Actual Size / zoom-in no longer stays soft — the display re-decodes at the resolution the zoom needs
- Edit dialog live preview (Curves, Color Corrections, Blur, Unsharp, Red Eye, …) stays sharp at 1:1 by processing only the on-screen part of the selection
- Saving next to the open file (typical ⌘S) no longer resets Save As’s last folder

## [1.0.2] — 2026-09-22

### Changed

- JPEG and TIFF default extensions are now `.jpg` / `.tif` (not `.jpeg` / `.tiff`)
- Opening a file checks that the content matches its type and suggests rename if not

### Fixed

- Saving an image no longer shows duplicate overwrite warnings
- Focus moves to the image window when an image is dropped from Finder onto the window
- Animated WebP plays correctly; fixes a decode backlog that could stall GIF/APNG afterward
- Multipage paging works the same for animated images as for PDF (↑/↓)

## [1.0.1] — 2026-09-21

### Added

- When opened from the disk image, MacViewPro offers to move itself to Applications, then relaunches and ejects the disk

### Fixed

- Avoids broken file associations from running (and registering) the app off a mounted DMG

## [1.0.0] — 2026-09-20

### Added

- Initial full release
