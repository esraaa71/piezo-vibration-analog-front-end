# Project Requirements — Revision 0.1

## Engineering problem
Build an analog front end for a piezoelectric vibration sensor, to convert small sensor charge into an oscilloscope/ADC-compatible voltage while controlling noise and signal bandwidth.

## Scope
1. LTspice design and simulation.
2. Sensor, feedback, filter and protection-component selection.
3. KiCad schematic and physical PCB design.
4. Electrical and physical validation with bench instruments.

## Provisional requirements

| ID | Requirement | Proposed value | Status |
|---|---|---|---|
| REQ-01 | Power input | Regulated +5 V | Simulated |
| REQ-02 | Signal reference | Buffered 2.5 V | Simulated |
| REQ-03 | Sensor | LDT0-028K piezo-film candidate | Not yet purchased or validated |
| REQ-04 | Useful signal band | Approximately 20–1000 Hz | Design target; not validated end-to-end |
| REQ-05 | Charge amplifier feedback | Rf 4.7 MΩ; Cf 2.2 nF | Simulated |
| REQ-06 | Filter | One 10 kΩ + 10 nF RC plus unity-gain buffer | Partially simulated |
| REQ-07 | Input protection | Must tolerate anticipated piezo pulses and unpowered conditions | Not designed |
| REQ-08 | Board | 2-layer custom PCB | Future |
| REQ-09 | Verification | Compare simulation, known charge injection, and sensor response | Future |

## Out-of-scope for first revision
- Embedded MCU analytics, bearing diagnosis, calibrated acceleration units or a commercial vibration-monitoring claim.
- A second RC filter or additional active stages unless testing indicates a clear need.

## Current design decision
For the first prototype, keep the charge amplifier and **one buffered RC filter**. Carry forward the ability to revisit filtering after noise/ADC requirements are clearer.

## Open engineering questions
- Will the mechanical mount provide an adequate 20–1000 Hz useful response for the chosen film sensor?
- What input protection limits piezo impulses without adding unacceptable leakage?
- What output voltage range and input impedance will the selected oscilloscope or ADC require?
- What sensor current/charge amplitudes are realistic under the intended mechanical conditions?
