# Survey Offset–RL input format

The drawing program uses a structured text file. The first field of each observation is an **offset** measured from the proposed road centreline, and the second is the observed **Reduced Level (RL)**. The initial set covers the left-hand-side data, including the centreline; the `R/S` marker then introduces right-side readings.

## Markers and concluding records

| Entry | Meaning |
|---|---|
| `PE` | Existing pavement edge, marked beside the relevant surveyed point |
| `R/S` | Start of right-side observations |
| `END` | End of surveyed observations |
| First line after `END` | Proposed road design RL for the current chainage |
| Final line | Current chainage reference |

The sample supplied by the author used fixed-width-looking numerical conventions, such as three digits before and three digits after the decimal point. The private routine expects a specific input format; **do not assume an arbitrary text file is accepted**.

## Example

See [synthetic_offset_RL_01+000.txt](../sample-data/synthetic_offset_RL_01%2B000.txt) for an illustrative, non-client example. It is **synthetic**, is not a validated engineering design and has not been tested with the proprietary program.

## Checks before running CC

1. Confirm offsets and RL readings against the survey record.
2. Confirm the correct side of the centreline and pavement-edge (`PE`) locations.
3. Check digit formatting and separators.
4. Ensure the maximum left/right offsets cover the designed side-slope extents and intersections with the existing terrain.
5. Check design RL and chainage identity.
6. Confirm the applicable pavement and cross-slope parameters, including changed geometry at curves.

This is a format guide, not a construction approval or substitute for survey quality assurance.
