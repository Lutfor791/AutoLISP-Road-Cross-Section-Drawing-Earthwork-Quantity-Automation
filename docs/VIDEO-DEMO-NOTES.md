# Road Cross-Section AutoLISP video demonstration

## Approved edited video

- **Working filename:** `AutoLISP_Road_Cross_Section_Demo.mp4`
- **Runtime:** 1 minute 49 seconds (109.4 seconds)
- **Format:** MP4 / H.264 / 1280 × 720
- **Content:** AutoCAD program introduction, Main Road and Service Road dialog settings, survey Offset–RL data, cross-section production and quantity-calculation demonstration
- **Editorial note:** The 43–50-second section of the review cut was replaced with a centered, readable Notepad Offset–RL example.
- **Review status:** The author approved the second edited version for presentation on November 23, 2026.
- **GitHub upload:** Pending. The approved video remains a separate file until uploaded to `assets/`.

The original screen recording is approximately **4 minutes 35 seconds**. The edited video is a demonstration of the existing program, **not** a distribution of its proprietary source code.

## Upload and README linking

1. Upload the approved MP4 to the repository's `assets/` folder using **Add file → Upload files**.
2. Confirm the exact filename and capitalization: `AutoLISP_Road_Cross_Section_Demo.mp4`.
3. Commit the uploaded file to the `main` branch.
4. Add a **Video Demonstration** section to `README.md`, linking to `assets/AutoLISP_Road_Cross_Section_Demo.mp4`.
5. Verify that the video opens and plays before changing the repository visibility to Public.

## Publication and disclosure checklist

- Confirm permission to publish the displayed project drawings, quantity tables and project references.
- Examine any visible file paths, organization names, personal identifiers or sensitive values in the recorded software interface.
- Keep proprietary AutoLISP/VLX source files, client DWGs and confidential survey datasets outside the public repository.
- Inspect the entire MP4 before publication, not merely the cover or selected frames.
- Verify linked media paths and README images after upload.
- Change repository visibility to Public only after this final review.

## Video outline

| Segment | Demonstration |
|---|---|
| Introduction | Project name and AutoCAD/AutoLISP automation purpose |
| Main Road | Geometry and pavement-layer parameter dialogs |
| Service Road | Widths, slopes, drain and layer-thickness dialogs |
| Survey input | Offset–RL data and markers; centered Notepad preview |
| Production | Drawing generation for one chainage |
| Quantities | Earthwork measurement and item-wise quantity calculations |
| Closing | Custom software for road construction workflows |

The program processes one chainage per execution by design. The Project Engineer reviews the initial outputs, and the CAD Engineer continues normal drawing production after confidence in the program is established. The `A1` command can measure any enclosed area but is used primarily for earthwork cut/fill areas in this application; `AT` sums left/right values.
