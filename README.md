# Circular Microstrip Patch Antenna for RFID at 2.45 GHz

Design and simulation of a compact, inset-fed circular microstrip patch antenna for RFID applications in the 2.45 GHz ISM band, using **CST Studio Suite**.

## Overview

The antenna is one of the main factors deciding an RFID system's read range, bandwidth and reliability. Circular microstrip patches offer a small footprint, low cost, easy integration with circuits and good impedance matching, which makes them a strong fit for 2.45 GHz RFID readers and tags.

## Design

![Antenna geometry in CST Studio Suite](images/geometry.png)

| Parameter | Value |
|---|---|
| Target frequency | 2.45 GHz |
| Substrate | FR4 (lossy) |
| Dielectric constant (εr) | 4.3 |
| Loss tangent (tan δ) | 0.02 |
| Substrate thickness (h) | 1.6 mm |
| Patch radius | 17.35 mm |
| Feed | 50 Ω inset microstrip line |
| Solver | Transient (broadband), 1.5 – 3.5 GHz |

The patch radius was calculated from the standard circular microstrip patch design equations, then refined in simulation.

## Results

| Metric | Result |
|---|---|
| Resonant frequency | ≈ 2.42 GHz |
| Minimum S11 | ≈ –15.5 dB |
| –10 dB bandwidth | ≈ 2.38 – 2.47 GHz |
| Minimum VSWR | ≈ 1.4 |
| Gain | 2.27 dBi |
| Directivity | 6.0 dBi |
| 3 dB beamwidth | 107.2° (φ = 0°), 90.9° (φ = 90°) |
| Side lobe level (φ = 90°) | –13.4 dB |
| Radiation efficiency | –3.73 dB |

### Return loss (S11)

![S11 plot](images/s11.png)

S11 dips to about –15.5 dB near 2.42 GHz and stays below the –10 dB benchmark from roughly 2.38 to 2.47 GHz, so the 2.45 GHz RFID frequency falls inside the matched band.

### VSWR

![VSWR plot](images/vswr.png)

The VSWR reaches its minimum at resonance, showing good impedance matching to the 50 Ω feed. Away from resonance the mismatch rises sharply, as expected for a narrowband patch.

### Radiation pattern

![3D directivity](images/directivity-3d.png)
![3D gain](images/gain-3d.png)

![Directivity, phi = 0](images/pattern-phi0.png)
![Directivity, phi = 90](images/pattern-phi90.png)
![Directivity, theta = 90](images/pattern-theta90.png)

The antenna radiates a wide broadside beam perpendicular to the patch, with 6 dBi directivity and 3 dB beamwidths of about 107° and 91° in the two principal planes. The wide beam gives broad coverage for reader–tag communication.

### Comparison with other RFID antennas

![Comparison with published RFID antennas](images/comparison-table.png)

## Repository Contents

```
├── images/     Geometry, S11, VSWR, radiation patterns, comparison table
└── report.pdf  Full project report
```

## Future Work

- Fine-tune the patch radius to shift the resonance from 2.42 GHz to exactly 2.45 GHz.
- Fabricate the antenna on FR4 and measure S11 and the radiation pattern with a vector network analyzer to compare against simulation.

## Author

**V Shruthi Shri**
