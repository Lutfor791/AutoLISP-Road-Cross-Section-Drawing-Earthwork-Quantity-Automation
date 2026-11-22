# Engineer-supervised cross-section workflow

The principal AutoLISP command, `CC`, **intentionally processes only one chainage per execution**. This permits engineering review of the source observations, changing design geometry, drawing and quantities.

## Recommended sequence

1. **Inspect field data** — check surveyed offsets, elevations, number formats, side split and pavement-edge markers.
2. **Confirm offset coverage** — the surveyed extremes on both sides must extend sufficiently for side-slope projection and the intended intersections with the existing ground.
3. **Review design parameters** — check road widths, wearing/binder/base/sub-base components as applicable, shoulders, drainage/median details, design RL and cross slopes.
4. **Adjust for road alignment** — apply section-specific cross slopes and superelevation changes where relevant, especially at curves.
5. **Run `CC` for the selected chainage** — produce the road cross-section and annotations.
6. **Inspect the generated section** — compare ground and proposed formation geometry against survey observations and design expectations.
7. **Review area/quantity calculations** — use `A1` to measure enclosed regions and `AT` to sum left/right quantities as appropriate.
8. **Revise and rerun if necessary** — correct data or parameters before moving to the next chainage, typically 20 m apart in the cited urban-road work.

This deliberately retains an engineer in the loop. **It does not claim automatic detection of all errors** and does not establish independently verified accuracy of calculated volumes or quantities.
