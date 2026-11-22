# CAD production workflow and initial engineering validation

This document records how the AutoLISP road cross-section program is used in practice. The main command, `CC`, **processes one chainage per execution by design**. It does not require ongoing supervision or sign-off by a Project Engineer on each generated section.

## Roles and sequence

1. **Surveyors — field measurements:** collect offsets from the proposed road centreline and Reduced Levels (RL) for the relevant chainages, then submit field records to the office.
2. **Data Entry Operators — preparation:** enter the surveyed observations and prepare correctly formatted input files for the AutoLISP program.
3. **AutoCAD Operator / CAD Engineer — drawing production:** check the required input format, enter road-design parameters in the dialogs, run `CC` to generate the individual cross-section drawing, and use `A1` / `AT` as needed for area measurement and left/right quantity summation.
4. **Project Engineer — initial validation:** examine a selection of the initial cross-section drawings and calculations. If the results are satisfactory, authorize the CAD Engineer to continue with the remaining sections.
5. **CAD Engineer — continued production:** generate drawings for subsequent chainages (typically at 20 m intervals in the described urban-road workflow) without Project Engineer review of every remaining drawing.

## Why CC processes one chainage at a time

The system could be designed to process an entire road in a batch, but the original author deliberately implemented individual-chainage execution to accommodate changing inputs and road geometry.

- Field observations must be entered in the expected **Offset–RL data format**.
- The most distant left and right observations must cover the design side-slope extents, including intersection with the existing ground.
- Parameters such as cross slope may need to change between chainages, especially where **superelevation** applies on curves.
- An operator can select the correct parameter values for the current section and proceed in sequence.

## Main operational risks identified by the developer

1. **Data entry and formatting errors** in the survey-data input files.
2. **Incorrect parameter values entered in the AutoCAD dialog boxes.**

These are the two principal identified error sources in the described workflow. The system automates drafting and associated calculations; it should not be presented as requiring independent Project Engineer checking of every section, or as automatically guaranteeing the validity of its inputs.

## Commands

| Command | Purpose |
|---|---|
| `CC` | Main cross-section drawing routine; one chainage per execution |
| `A1` | Enclosed-area measurement, including earthwork cut/fill areas |
| `AT` | Sum left-side and right-side values |

The source code is proprietary and is not part of this documentation-only repository.
