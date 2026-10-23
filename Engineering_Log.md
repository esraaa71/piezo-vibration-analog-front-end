# Engineering Log

## Project: Smart Vibration Sensor Analog Front-End

### Initial design choices
- 5 V single-supply power.
- Two equal 10 kΩ resistors for 2.5 V midpoint.
- AD8608 model for buffered reference, charge converter and output buffer.
- Rf 4.7 MΩ / Cf 2.2 nF charge amplifier.
- First-order low-pass RC: 10 kΩ / 10 nF.
- Simplified piezoelectric current source with 480 pF parallel capacitance; planned real sensor LDT0-028K.

### Why one RC section for now?
A second low-pass stage was temporarily explored, but is not yet justified by a measured noise or ADC rejection requirement. The frozen first-prototype design should keep one RC filter buffered by U3.

### Limitations to mention publicly
- All results currently LTspice-only.
- The simulation input source is an electrical approximation and does not validate vibration magnitude or sensor mechanical bandwidth.
- No overvoltage/ESD protection design has yet been finalized.
- No PCB, BOM, hardware measurements, or manufacturing files exist yet.

### Engineering entries

#### 2026-10-21 — Voltage reference
**Test:** DC operating point.  
**Observation:** 5.0 V supply; 2.5 V midpoint; 0.25 mA through each 10 kΩ resistor.  
**Learning:** Voltage-divider loading can be reduced through a unity-gain follower.

#### 2026-10-21 — Reference buffer
**Test:** AD8608 follower operating point and 10 kΩ test-load experiment.  
**Observation:** VREF_BUF ≈ 2.49992 V; load current ≈0.25 mA.  
**Learning:** Buffer output provides load current while minimally loading the midpoint network.

#### 2026-10-21 — Charge amplifier
**Test:** DC operating point and transient for 100 nA peak at 100 Hz.  
**Observation:** V(CHARGE_OUT) ≈2.49984 V without signal; at 100 Hz sinusoidal excitation the settled output is approximately 2.43–2.57 V. Startup transient is visible.  
**Learning:** Feedback capacitance determines charge-to-voltage sensitivity; feedback resistance defines decay / low-frequency behavior.

#### 2026-10-21 — Output RC filter
**Test:** AC sweep and ratio `V(filtred)/V(charge_out)`.  
**Observation:** Low-pass response agrees qualitatively with a 10 kΩ / 10 nF first-order RC section.  
**Learning:** Normalizing output by input isolates an individual filter's response from the complete signal chain.

### New entry template
Date: YYYY-MM-DD  
Milestone:  
Question/hypothesis:  
Schematic revision:  
Simulation directive and source:  
Measurements (units):  
Expected vs observed:  
Issue/limitation:  
Next step:  
Evidence file(s):
