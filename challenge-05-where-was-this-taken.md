# Challenge 05 — Where Was This Taken?

**Category:** OSINT (Open-Source Intelligence)

## Objective
Identify a historic institutional building from an image after GPS and camera EXIF metadata have been removed.

## Clues Provided
- Historic stone facade and clock tower
- Arched entrance features
- The institution's history dates to 1865
- The building is on the COEP campus in Pune

Target image supplied by the challenge:

`https://cybercell.coeptech.ac.in/mini-ctf/c5/location.jpg`

## Investigation Procedure
1. Download the target image and keep the original unchanged.
2. Check for remaining metadata:

   ```bash
   exiftool location.jpg
   ```

3. Use [Google Lens](https://lens.google.com/) to reverse-search the image.
4. Compare architectural details such as the number and shape of arches, tower placement, windows, and stonework.
5. Search public sources, prioritizing official COEP university history pages and photographs. Useful search phrases include:
   - `COEP Pune historic main building 1865`
   - `COEP Technological University heritage architecture`
   - `COEP Pune main building clock tower`
6. Compare the target image against independent references and confirm the common name.
7. Submit the correctly formatted flag to the CTF platform.

## Proposed Identification
The clues suggest the historic **Main Building** of COEP Technological University.

Proposed flag format:

```text
COEP{main_building}
```

## Verification Status
**Proposed; not independently confirmed by the challenge platform in these notes.** Record whether the platform accepts the flag and preserve the evidence used to identify the building.

## What I Learned
- OSINT combines publicly available evidence to investigate a subject.
- Reverse image search can surface similar images and candidate locations.
- Architectural features can remain identifying even after metadata is removed.
- Multiple independent clues provide stronger evidence than a visual guess alone.

## Privacy Note
Removing EXIF metadata reduces exposure of embedded location information, but distinctive visual landmarks may still reveal where a photograph was taken.
