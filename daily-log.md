# Daily Log

##July 23, 2026
- Started Vision model research
- Next: Test zero-shot classification on dormancy images.
- Ran organize_photos.py against SSD photo dump. Filename patterns found:
  - NO_PREFIX: 427 images (e.g. take_a_photo_of_the_quadrat-20250701-192030.jpg)
  - IMG_: 263 images (e.g. IMG_20250519_153331125_HDR.jpg)
  - PXL_: 200 images (e.g. PXL_20240711_181333248.jpg)
  - All three patterns embed a YYYYMMDD date in the filename itself — can likely parse dates directly from filenames instead of relying on EXIF.
- Plan: organize photos by date — split into 2024 and 2025, then by month within each year.
- Split organize_photos.py into survey_photos.py (the pattern-survey script, now pointed at the real SSD path and skipping macOS junk files) and an empty organize_photos.py reserved for the actual date-based mover.
- Reviewed sage-image-test.py (pulls W083 bottom-camera images via sage_data_client): found a critical bug, `row[value]` referenced an undefined name instead of the string `'value'`, which silently failed every row via the outer try/except.
- After fixing that, hit HTTP 401 downloading images. Root cause: the SAGE metadata query is public, but the actual image files on storage.sagecontinuum.org require SAGE portal auth (SAGE_USER/SAGE_TOKEN) — the script never sent credentials.
- Adapted a colleague's working script (now data_pull.py) that authenticates via `curl -u SAGE_USER:SAGE_TOKEN -L` (follows redirect to NRP's signed URL) and validates JPEG magic bytes after download.
- Merged that auth fix with the original goals: 6 target survey dates (2025-05-20, 06-05, 06-17, 07-01, 07-30, 08-07), each windowed 08:00-20:00, downloaded into per-date folders on the SSD, with running downloaded/failed totals.
- Added a .gitignore (`.env`) so SAGE credentials never get committed — data_pull.py reads them from a local .env or exported env vars.
- Next: run data_pull.py locally with real SAGE_USER/SAGE_TOKEN, confirm images land correctly in per-date SSD folders, then build the actual organize_photos.py mover for the existing (non-SAGE) photo dump.

## End of session
- Ran data_pull.py with real SAGE credentials — all 6 date folders now exist under /Volumes/SSK SSD/sage_images (2025-05-20, 06-05, 06-17, 07-01, 07-30, 08-07).
- Both repos committed and pushed. sage-summer-camp-2026 needed a merge first — a collaborator had updated project-organization-notes.md there (team member name split) via PR #1; merged cleanly, no conflicts.
- Picking up tomorrow:
  1. Check data_pull.py's downloaded/failed counts per date folder — confirm nothing silently failed.
  2. Spot-check a few downloaded JPEGs open correctly.
  3. Build out organize_photos.py: parse the YYYYMMDD date from each of the three filename patterns (IMG_, PXL_, NO_PREFIX) in the original ~890-image SSD dump and move/copy into YYYY/MM folders.
  4. After that, revisit zero-shot classification test on dormancy images.
