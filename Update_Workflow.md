# Updating GitHub and LinkedIn for Each Milestone

## Every meaningful LTspice / PCB change

1. Save the changed `.asc` file in `03_LTspice/` (or KiCad source in `04_KiCad/` later).
2. Take a **clear, cropped screenshot** of the schematic and relevant waveform; add to `media/` using descriptive filenames.
3. Add one entry in `docs/Engineering_Log.md`: objective, what changed, results, unresolved issue, next step.
4. Update the relevant line in `docs/Simulation_Results.md` with proper units.
5. Update `CHANGELOG.md` with the completed, verified change.
6. Update `README.md` only when the headline progress / core architecture changes.
7. Commit with a concrete message such as `sim: verify first RC filter response` or `docs: add sensitivity sweep evidence`.
8. Push to GitHub.

## What to publish on LinkedIn

- Keep one **Projects** entry pointing to the GitHub repository; update its short description only at major stages.
- Publish **progress posts only for meaningful milestones**, not every resistor edit. Suggested future stages: verified complete LTspice signal chain, KiCad PCB design, fabricated board, bench-measured results.
- For every post: describe *problem → change → evidence → next step*. Avoid promising unachieved results.

## Suggested commit messages

- `docs: initialize LTspice vibration AFE portfolio`
- `sim: add AD8608 buffered reference`
- `sim: verify charge amplifier transient response`
- `sim: compare feedback capacitor sensitivity`
- `sim: evaluate single-stage RC filter AC response`
- `design: add input protection and supply decoupling` (ONLY once actually done)
- `pcb: add KiCad schematic and layout` (ONLY once actually done)
- `test: add bench-measured reference and signal response` (ONLY once actually done)

## Immediate action
Copy the original, **working** LTspice `.asc` file into `03_LTspice/`. The package has screenshots but no user's original LTspice schematic bytes. Update files after each checkpoint using the checklist above.
