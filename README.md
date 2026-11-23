

https://github.com/user-attachments/assets/ceee498f-d5a5-48d9-952d-2160441af02a

# AutoLISP Program for Road Cross-Section Drawing & Earthwork Quantity Calculations

![AutoLISP program for road cross-section drawing and earthwork calculations](assets/00-project-cover-updated.svg)

**AutoCAD/AutoLISP automation for road cross-section drawings and earthwork quantity calculations, with operator-controlled chainage processing.**

This portfolio project documents a custom AutoLISP program developed for road construction contractors to produce project-specific drawings and calculations. It supports cross-sections at approximately **20-metre chainage intervals** in urban areas. It uses surveyed **offset and Reduced Level (RL)** observations and configurable road-design parameters. The main routine deliberately draws **one chainage per execution**, allowing the CAD Operator/CAD Engineer to enter suitable design parameters, process individual sections and continue producing drawings. The Project Engineer checks a selection of initial drawings and calculations to establish confidence in the program; once satisfied, the CAD Engineer proceeds without requiring approval of every subsequent section.

> **Portfolio documentation only.** The original AutoLISP source code, program files, client DWGs and unedited screen recording are not distributed here. This repository is not a runnable software release.

## Video demonstration

[**Watch the approved AutoLISP Road Cross-Section Demonstration (1 min 49 sec)**](assets/AutoLISP_Road_Cross_Section_Demo.mp4)

[![Preview of the generated road cross-section and quantity table — select to watch the demonstration](assets/03-generated-section-and-quantities.PNG)](assets/AutoLISP_Road_Cross_Section_Demo.mp4)

The short video shows the custom AutoCAD/AutoLISP program's parameter dialogs for the Main Road and Service Road, the surveyed Offset–RL data input, cross-section drawing, and associated quantity-calculation workflow. The example illustrates **one-chainage-at-a-time** operation, with CAD-operator-controlled design settings and subsequent drawing production.

*The video documents program operation only; the proprietary AutoLISP source code is not included.*

## Project overview

| Attribute | Details |
|---|---|
| Domain | Road construction; civil engineering CAD |
| Technology | AutoCAD and AutoLISP |
| Typical section spacing | 20 m in the cited urban-road workflow |
| Data input | Survey offsets and elevations (RL), pavement-edge markers, right-side separator, design RL and chainage |
| Key operations | Cross-section drafting, area calculation and left/right quantity summation |
| Approach | Operator-controlled, one-chainage processing; initial Project Engineer validation |
| Source availability | Proprietary; not published |

## Three AutoLISP commands

| Command | Function |
|---|---|
| `CC` | **Main command**: generates the road cross-section drawing for one chainage using survey observations and design parameters. |
| `A1` | Calculates the area of **any enclosed boundary**; in this road cross-section program, it is mainly used to measure **earthwork cut and fill areas**. |
| `AT` | Sums corresponding quantities from the left-hand and right-hand sides. |

The commands are part of the author's own AutoCAD program and **cannot be run by downloading this documentation repository**.

## Demonstrated technical capabilities

- Work with field-survey offset–RL measurements.
- Configure drawing parameters for the road section, including cross slopes, pavement widths, side slopes and other road components.
- Draw and annotate existing terrain and proposed road cross-section geometry.
- Represent roadway components and provide drawing-level dimensional and elevation information.
- Measure enclosed areas using `A1` (primarily earthwork cut and fill areas in this program) and sum corresponding left/right quantities with `AT`.
- Adjust section-specific parameters when terrain or road geometry changes.

## Actual production workflow

1. **Field Surveyors** collect survey offsets and Reduced Levels (RL) and submit field records to the office.
2. **Data Entry Operators** enter the survey observations and format the text files to meet the routine's input requirements.
3. **AutoCAD Operator / CAD Engineer** selects the chainage, enters appropriate design parameters in the program dialogs, and executes `CC` to produce the cross-section drawing and its associated calculations. The `A1` command measures enclosed areas, primarily cut/fill areas in this application; `AT` sums left/right values.
4. **Project Engineer** verifies a selection of initial cross-section drawings and calculations. When satisfied with their correctness and the program's performance, the Project Engineer authorizes continued production.
5. **CAD Engineer** prepares the remaining cross-sections by running the program chainage by chainage. **Routine Project Engineer approval of each subsequent drawing is not required** after confidence in the program has been established.

## Why one chainage per execution?

The one-chainage design is **intentional operator-controlled automation**, not an inability to process the full road. It allows the CAD Operator to work with section-specific survey and design inputs, particularly where cross slopes or superelevation vary on curves, and helps avoid carrying an incorrect parameter setting across multiple sections.

In the established workflow, the author identifies **two principal operational error sources**:

- **Data entry / formatting:** errors when field survey observations are entered or prepared in the text format required by the program. The survey offsets must also cover the designed side-slope extents.
- **Design-parameter entry:** incorrect values entered into the program's dialog boxes, including section-specific parameters such as cross slopes.

The purpose of the per-chainage execution is to maintain appropriate control over changing inputs and parameters. It **does not mean the Project Engineer personally inspects every produced drawing**, and the repository does not claim that the program independently detects all input errors.

## Input-data format

The supplied project example is a text file using **offset** in the first column and **RL** in the second. The format also uses:

- `PE`: existing pavement-edge marker
- `R/S`: start of observations on the right-hand side
- `END`: end of observed point records
- Line immediately after `END`: proposed-road **design RL**
- Final line: **chainage identifier**

For a **synthetic documentation example**, see [sample-data/synthetic_offset_RL_01+000.txt](sample-data/synthetic_offset_RL_01%2B000.txt). The sample is illustrative and has not been tested with the proprietary routine.

## Documentation

- [Offset–RL format explained](docs/INPUT-DATA-FORMAT.md)
- [CAD production and initial engineering validation workflow](docs/QUALITY-CONTROL-WORKFLOW.md)
- [Demonstration-video and disclosure checklist](docs/VIDEO-DEMO-NOTES.md)

## Road cross-section demonstrations

The following selected images document the engineering interface and generated output of the AutoLISP workflow. They are **portfolio illustrations, not independently verified as-built measurements**.

### 1. Program Startup Dialog

![Program Startup Dialog — Road Cross Section SDSCRIP](assets/07-program-startup-dialog.svg)

The **Road Cross Section (SDSCRIP V1.0)** dialog is the main control interface for command `CC`. It provides separate buttons for Main Road and Service Road **Widths and Slopes** and **Thickness**, horizontal and vertical drawing-scale inputs, a choice to enter the Design RL manually or read it from the survey-data file, and controls for selecting, previewing, or editing the Offset–RL input file.

*This dialog illustration reproduces the layout and example settings of the screenshot supplied by the author; it is not a direct screenshot.*

### 2. Main Road Parameters — Widths and Slopes

![Main Road Widths and Slopes dialog recorded in AutoCAD](assets/01-main-road-design-parameters.png)

The Main Road dialog configures the median, left/right pavement widths and cross slopes, W-beam widths/slopes, soft-shoulder widths/slopes, and left/right side slopes. In the recording, the example includes **9,400 mm pavement widths on both sides**, **−3.0% pavement cross slopes**, **2,000 mm soft shoulders**, and **1 in 2 side slopes**. All values are project-specific and may vary at different chainages.

### 3. Main Road Layers / Thickness

![Main Road Layers and pavement thickness settings](assets/08-main-road-layers.svg)

The Main Road Layers dialog defines the thickness of individual pavement layers. The recorded example shows:

| Main Road pavement layer | Thickness (mm) |
|---|---:|
| Wearing Course | 50 |
| Binder Course | 160 |
| Base Type-I | 300 |
| Sub-base | 250 |
| ISG | 300 |

*Vector reconstruction of the recorded Main Road Layers dialog; values are illustrative.*

### 4. Service Road Parameters — Widths, Slopes and Drains

![Service Road left and right widths, cross slopes and drain parameters](assets/09-service-road-widths-slopes-drains.svg)

The Service Road dialog contains separate inputs for **left and right Service Road widths and cross slopes**, together with **Drain-1 heights** and **Drain-2 widths**. The recorded example shows:

| Service Road setting | Left | Right |
|---|---:|---:|
| Width (mm) | 7,300 | 7,300 |
| Cross slope (%) | −3.0 | −3.0 |
| Drain-1 height (mm) | 600 | 600 |
| Drain-2 width (mm) | 300 | 300 |

*Vector reconstruction of the recorded Service Road Parameters dialog.*

### 5. Service Road Layers / Thickness

![Service Road Layers and pavement thickness settings](assets/10-service-road-layers.svg)

The Service Road Layers dialog sets the layer thicknesses independently from the Main Road:

| Service Road pavement layer | Thickness (mm) |
|---|---:|
| JRCP | 270 |
| Lean Concrete | 100 |
| Sub-base | 250 |
| ISG | 300 |

*Vector reconstruction of the recorded Service Road Layers dialog; figures are example design settings, not standard values for all projects.*

### Road cross-section details

![AutoCAD road profile close-up](assets/02-road-profile-closeup.png)

The drawing represents existing field ground and proposed road geometry, with elevations and annotations.

### Generated section and earthwork quantities

![Generated road cross-section and earthwork quantities at Chainage 21+180](assets/03-generated-section-and-quantities.PNG)

This drawing presents the complete road cross-section together with the corresponding item-wise quantity table for Chainage 21+180. It demonstrates the program's integrated AutoCAD drafting and quantity-calculation workflow, including the existing ground profile, proposed road geometry, design and existing RL/offset information, and left-side, right-side and total quantities.

### Quantity calculation table

![Road-section quantity table](assets/04-quantity-table.png)

The CAD Operator/CAD Engineer uses `A1` primarily to calculate earthwork **cut and fill areas**, although it can measure **any enclosed area**. The `AT` command combines corresponding left- and right-side quantity values.

### Illustrative survey data format

![Offset RL data format illustration](assets/05-illustrative-data-format.png)

The field-data format captures offsets and RL values, with section markers and design information. The graphic is an explanation of input structure, not a substitute for the original survey records.

The approved [video demonstration](assets/AutoLISP_Road_Cross_Section_Demo.mp4) is included in the repository. The original unedited screen recording and proprietary AutoLISP source code are not distributed. See [video and publication notes](docs/VIDEO-DEMO-NOTES.md).

## Engineering and technical focus

`AutoLISP` · `AutoCAD` · `Road Cross-Sections` · `Survey Offset–RL` · `Earthwork Quantities` · `Cut and Fill` · `CAD Automation` · `Operator-Controlled Automation` · `Initial Engineering Validation`

## Authorship

Developed and documented by **Md. Lutfor Rahman** as part of professional CAD and engineering-automation work. The repository demonstrates the engineering workflow and the author's relevant experience rather than distributing a licensed implementation.

For suitable custom AutoCAD automation or civil-engineering drafting work, contact the author through his professional profile.
