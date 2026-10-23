# Changelog — Piezoelectric Vibration Analog Front-End

Log **completed and verified simulation steps**, not intended outcomes. Dates refer to progress reported during this project.

## 2026-10-23 — Documentation starter
- Created a GitHub-ready README, screenshots, references, and milestone-tracking files.
- Recorded outstanding design-validation items before PCB development.
- Prepared LinkedIn text without claiming physical hardware results.

## 2026-10-21 — LTspice design milestones
- Built a 5 V source and 10 kΩ/10 kΩ mid-supply voltage divider (`VREF = 2.5 V`).
- Added an AD8608 voltage follower to buffer the reference (`VREF_BUF ≈ 2.49992 V`).
- Simulated a 10 kΩ buffer load; buffered voltage stayed near 2.5 V.
- Added charge amplifier with `Rf = 4.7 MΩ` and `Cf = 2.2 nF` (`CHARGE_OUT ≈ 2.49984 V` in DC operating-point simulation without sensor excitation).
- Simulated a 100 nA peak, 100 Hz current-source input; added a simplified 480 pF sensor capacitance in parallel and 4.7 kΩ input series resistance.
- Observed a settling output waveform approximately 2.43–2.57 V around a 2.5 V bias.
- Explored changing Cf and observed increased output amplitude with lower feedback capacitance.
- Ran AC sweeps to investigate the charge-amplifier transimpedance and RC-filter response.
- Added a first RC filter (`10 kΩ + 10 nF`) and U3 voltage follower.
- Tried an additional RC stage as an experiment; decided not to retain it in the initial design unless results justify it.

## Next milestone — Pending
- Confirm final single-RC filter schematic and run `V(AFE_OUT)` transient and frequency-response plots.
- Review sensor overvoltage protection and decoupling.
