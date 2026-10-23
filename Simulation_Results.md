# LTspice Simulation Results — Recorded to Date

**All numerical observations below are simulated or estimated from screenshots, not bench measurements.**

| Test | Conditions | Observed / calculated result | Evidence |
|---|---|---|---|
| Divider .op | 5 V, 10 kΩ + 10 kΩ | VREF = 2.500 V; 0.25 mA divider current | [Operating point screenshot](../media/voltage_reference_op.png) |
| Buffer .op | AD8608 unity gain | VREF_BUF ≈ 2.49992 V | [Buffer load screenshot](../media/buffer_load_op.png) |
| Buffer load | 10 kΩ output-to-ground | VREF_BUF ≈ 2.49992 V; I(load) ≈ 0.249992 mA | [Buffer load screenshot](../media/buffer_load_op.png) |
| Charge amplifier .op | Rf 4.7 MΩ, Cf 2.2 nF, no sensor excitation | CHARGE_OUT ≈ 2.49984 V | Reported DC results |
| Charge transient | I1 = 100 nA peak, 100 Hz; Cs = 480 pF; Rin = 4.7 kΩ | ~2.43–2.57 V steady-state (visually estimated) | [Waveform](../media/charge_amplifier_transient.png) |
| Feedback capacitor sensitivity | Cf lowered from 2.2 nF (separate exploratory run) | Larger output-signal amplitude | [Exploratory waveform](../media/cf_sensitivity.png) |
| Feedback corner | Rf 4.7 MΩ, Cf 2.2 nF | Theoretical 15.4 Hz; reported magnitude around −9.66 dBV near that frequency using current source | User-reported cursor observation, to recheck |
| First RC corner | 10 kΩ, 10 nF | Theoretical ~1.592 kHz; AC ratio plot supports expected low-pass behavior | [AC response](../media/filter_ac_response.png) |

## Calculation notes

Ideal charge conversion: `ΔVout = −ΔQ/Cf` (valid in appropriate frequency range).  
Feedback time constant: `Rf × Cf = 10.34 ms`.  
Feedback-network corner: `1/(2π Rf Cf) ≈ 15.4 Hz`.  
One-stage RC corner: `1/(2π × 10 kΩ × 10 nF) ≈ 1592 Hz`.

## Important measurement distinction

The source has a constant **current** AC amplitude, so `V(charge_out)` is the *voltage response to that specified current input*, not an acceleration sensitivity plot. To isolate the output filter use `V(filtred)/V(charge_out)`; to measure transimpedance use `V(charge_out,vref_buf)/I(I1)` with explicit units V/A. The sign and the source's LTspice current-reference direction need to be checked.

## Next capture requested
- Freeze single-filter version, label final output `AFE_OUT`, and capture `.op`, `.tran`, `.ac` plots.
- Record cursor-based -3 dB points for first RC ratio.
- Save plot settings and full `.asc` LTspice project for reproducibility.
