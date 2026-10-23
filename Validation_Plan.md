# Validation Plan

## Before committing to PCB

- [ ] Save single-filter schematic version and remove exploratory R5/C3 from the initial design if still present.
- [ ] Add supply bypass and reference decoupling capacitors; validate startup and loading.
- [ ] Develop a practical piezo sensor equivalent, including relevant sensor capacitance/leakage and loading considerations.
- [ ] Study source current range and charge amplitude to ensure output does not clip under realistic excitation.
- [ ] Design and verify a low-leakage input-protection strategy suitable for powered and unpowered conditions.
- [ ] Run `.op`, `.tran`, `.ac`, and, where models support it, `.noise` analyses.
- [ ] Test component tolerances and verify amplifier stability.
- [ ] Select real footprints, connectors, capacitors (C0G preferred for Cf), and realistic part numbers.

## PCB phase (not started)

- [ ] Create KiCad schematic for one physical quad AD8608 package, carefully mapping U1/U2/U3 sections.
- [ ] Add input test connector, calibration input, supply input, output connector and test points.
- [ ] Use a short, clean high-impedance input path; review guard-ring and leakage considerations.
- [ ] Add proper 100 nF local decoupling close to the amplifier supply pins.
- [ ] Run ERC, DRC and BOM review; generate Gerbers.

## Hardware phase (not started)

- [ ] Power up with supply current limiting.
- [ ] Verify VREF and VREF_BUF voltage levels.
- [ ] Inject a controlled known charge through a precision calibration capacitor.
- [ ] Measure frequency response of filter and charge amplifier.
- [ ] Evaluate output noise and mechanical sensor response with a repeatable fixture.
- [ ] Compare simulations with physical measurements and document discrepancies.

## Caveats
A flexible piezoelectric film is not inherently a calibrated accelerometer; mounting, temperature and resonance affect physical response. Safe design requires protection against sensor-generated transients before a real sensor is connected.
