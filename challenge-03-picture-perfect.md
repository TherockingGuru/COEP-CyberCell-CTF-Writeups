# Challenge 03 — Picture Perfect

**Category:** Digital Forensics

## Objective
Investigate a photograph for metadata that may reveal information beyond its visible pixels.

## Investigation Procedure
1. Download the image from the authorized CTF environment.
2. Identify the file type:

   ```bash
   file mystery.jpg
   ```

3. Inspect metadata:

   ```bash
   exiftool mystery.jpg
   ```

4. Look for relevant fields such as camera make/model, timestamps, GPS coordinates, software tags, or unusual comments.
5. Search for printable strings:

   ```bash
   strings mystery.jpg
   ```

6. Record any actual clue or flag found and verify it against the challenge.

## Result / Flag
**Pending verification.** The challenge card describes EXIF metadata extraction, but the actual target output and flag have not been provided in these notes. Add the observed evidence and exact flag after running the commands on the downloaded artifact.

## What I Learned
- Image files can contain metadata in addition to pixel data.
- EXIF metadata can sometimes expose timestamps, device information, or location.
- `exiftool` parses metadata; `strings` extracts sequences of printable characters.
- Metadata may be absent or deliberately stripped, so results must be verified.

## Tools
- `file`
- ExifTool
- `strings`
