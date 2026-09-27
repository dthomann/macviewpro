# Changelog

All notable user-facing changes are listed here. Dates are release dates (local).

## [1.1.0] — 2026-09-27

### Added

- Batch conversion / rename (B, File menu): convert many files at once with the same format options as Save As, optionally resize (fit within, long edge, percent, only shrink), rotate / flip, auto-crop, grayscale or negative, rename with patterns, and choose the destination and overwrite behaviour. Files that can't be converted are flagged when added, and a log lists the results
- Save As and batch convert can write BMP and AVIF. AVIF appears only on Macs whose system can encode it
- Animations are saved whole: GIF, APNG and HEICS save in their own format, and Save As writes animated GIF, APNG or HEICS with every frame, its timing and the loop count. Animated WebP and AVIF files can be saved as animated GIF, APNG or HEICS with Save As
- Multipage TIFF and HEIC collections are saved whole, and Save As can write multipage TIFF or HEIC
- Edit the pages of a multipage TIFF or HEIC one at a time, each with its own undo. Edit ▸ Apply Edits to All Pages makes edits, undo and Revert act on every page. Saving writes the edited pages and keeps the others untouched
- File ▸ Extract Pages / Frames… saves every page, frame or icon size as its own file (name-001, name-002, …) in a new folder, in the original's format by default or any format you choose
- HEICS and animated AVIF files play like other animations
- ICO and ICNS icons open at their largest size, which is also what editing and Save As use
- Lossless JPEG rotate and flip: when a JPEG has only been rotated or flipped (L, R, H, V) and is saved as JPEG, Save and Save As now write it without re-encoding, so there is no quality loss, and the status bar says "Saved losslessly". The EXIF orientation is reset and the embedded EXIF preview thumbnail is removed, so other apps don't show the old orientation
- The Save sheet's "Keep EXIF / IPTC / XMP / ICC" option is now available for PNG, TIFF, HEIC and AVIF as well as JPEG, and the EXIF thumbnail follows it. Formats that can't store metadata (GIF, WebP, BMP) say so
- PNG is always saved at maximum compression (level 9); the compression level option is gone
- Lossless JPEG Operations: rotating a JPEG whose size doesn't fit the JPEG block size now re-encodes it instead of trimming edge pixels, unless you tick "Trim partial edge blocks instead of re-encoding". JPEGs rotated by their EXIF orientation are now transformed losslessly too, instead of always being re-encoded. An existing ".lossless" file is no longer overwritten; a free name is used instead
- Save As from bare S remembers the folder you chose, even when it's the image's own folder

### Fixed

- The "Save changes?" prompt now offers Save As… instead of overwriting the original, so an edited RAW, PSD or PDF is no longer overwritten with JPEG data
- Saving an edited animation or multipage file never writes just one frame or page
- Menus now disable Save, Save As and editing where they can't work (for example a PDF), and the status bar says why
- Fixing a wrong file extension no longer replaces an existing file with the same name; it offers a free name instead
- A new window no longer sometimes shows an empty canvas until you interact with it
- The welcome screen no longer overlaps its title and photo in small windows
- Installing over an existing copy of the app moves the old copy to the Trash instead of deleting it

### Notes

- Animations and PDFs can't be edited. PDFs can't be saved; use Extract Pages / Frames… to export their pages
- Batch conversion flags and skips animated and multipage files for now
- AVIF quality is capped at 99, since the system's encoder rejects 100
- Lossless JPEG saves copy the original's metadata and colour profile unchanged, so they are used only when "Keep EXIF / IPTC / XMP / ICC" is ticked and the colour profile is Original, and only when the width and height fit the JPEG block size (multiples of 8 or 16 px). Otherwise the file is re-encoded, so no pixels are ever trimmed and unticked metadata is really removed. Any other edit, and batch rotate / flip, re-encode the file as before
- Resizing is limited to 400 megapixels per image. Batch skips files whose result would be larger, and the Resize dialog asks for a smaller size
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
