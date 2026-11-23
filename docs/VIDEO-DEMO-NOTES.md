# Road Cross-Section AutoLISP video demonstration

## Approved edited video

- **Working filename:** `AutoLISP_Road_Cross_Section_Demo.mp4`
- **Runtime:** 1 minute 49 seconds (109.4 seconds)
- **Format:** MP4 / H.264 / 1280 × 720
- **Content:** AutoCAD program introduction, Main Road and Service Road dialog settings, survey Offset–RL data, cross-section production and quantity-calculation demonstration
- **Editorial note:** The 43–50-second section of the review cut was replaced with a centered, readable Notepad Offset–RL example.
- **Review status:** The author approved the second edited version for presentation on November 23, 2026.
- **GitHub upload:** Completed. `assets/AutoLISP_Road_Cross_Section_Demo.mp4` is available and linked from `README.md`.

The original screen recording is approximately **4 minutes 35 seconds**. The edited video is a demonstration of the existing program, **not** a distribution of its proprietary source code.

## Video file and README integration

The approved MP4 has been uploaded to `assets/AutoLISP_Road_Cross_Section_Demo.mp4`. A **Video demonstration** section near the start of `README.md` links to the video through both text and an annotated cross-section preview image. Before changing repository visibility to Public, open the video on GitHub and confirm that it plays correctly.

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
