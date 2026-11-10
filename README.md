# VR Time Perception Eye-Tracking Dataset

Raw eye-tracking data for the study: "Decoding Time Perception in Virtual Reality: How Extreme Brightness and Eye Movements Shape Temporal Experience"

## Citation

Park, J., & Rhee, C. (2025). Decoding Time Perception in Virtual Reality: How Extreme Brightness and Eye Movements Shape Temporal Experience. *International Journal of Human-Computer Interaction*. [https://doi.org/10.1080/10447318.2025.2598115]

## Dataset Overview

- **File:** `vr-time-perception-data.csv`
- **Format:** CSV (UTF-8 encoding)
- **Size:** Approximately 25 MB
- **Total observations:** 339,983 eye-tracking events
- **Participants:** 26 adults (14 males, 12 females; mean age = 22.3 years)
- **Sampling rate:** ~100 Hz (Tobii Pro Glasses 2)

## Experimental Design

- **Display types:** 2 (HMD: Pico Neo3 PRO Eye; PC: 27-inch monitor)
- **Brightness modes:** 3 (Night ≈ 4 cd/m², Dark ≈ 35 cd/m², Fullbright ≈ 250 cd/m²)
- **Total conditions:** 6 (2 × 3 within-subjects design)
- **Trial duration:** 60 seconds per condition

## Variables

| Variable | Type | Description | Example Values |
|----------|------|-------------|----------------|
| **ID** | Integer | Participant identifier | 1-26 |
| **Group** | Integer | Device condition code | 1 = HMD (Experimental)<br>0 = PC (Control) |
| **Event** | String | Experimental condition combining device and brightness mode | `Ex_Nightmode`<br>`Ex_Darkmode`<br>`Ex_Fullbrightmode`<br>`Co_Nightmode`<br>`Co_Darkmode`<br>`Co_Fullbrightmode` |
| **Pupil Average(m/m)** | Float | Mean pupil diameter in millimeters | 3.5 - 6.5 mm<br>(typical range) |
| **Eye movement type** | String | Classification of gaze event | `Saccade` (38,985)<br>`Fixation` (281,306)<br>`Unclassified` (19,691)<br>`EyesNotFound` (1) |
| **Gaze event duration(ms)** | Integer | Duration of the gaze event in milliseconds | 20-2000+ ms |
| **Timepass(Seconds)** | Integer | Elapsed time since trial start | 0-180 seconds |
| **group** | String | Device condition label (human-readable) | `Exp` = HMD<br>`Control` = PC |

## Data Summary

### Eye Movement Events
- **Saccades:** 38,985 (11.5%)
- **Fixations:** 281,306 (82.7%)
- **Other events:** 19,692 (5.8%)

### Pupil Size Statistics
- **Overall:** 4.56 ± 0.82 mm (Mean ± SD)
- **HMD group:** 5.14 ± 0.76 mm
- **PC group:** 4.13 ± 0.57 mm

### Distribution by Brightness Mode
- **Night mode:** 111,260 events (32.7%)
- **Dark mode:** 114,874 events (33.8%)
- **Fullbright mode:** 113,849 events (33.5%)

### Distribution by Device
- **HMD (Experimental):** 144,177 events (42.4%)
- **PC (Control):** 195,806 events (57.6%)

## Data Collection

Eye-tracking data were collected using Tobii Pro Glasses 2 with a sampling rate of approximately 100 Hz. Participants wore the eye-tracking glasses while viewing content through either:
1. An HMD (Pico Neo3 PRO Eye) in a fully immersive environment, or
2. A 27-inch PC monitor in a standard laboratory setting

Each participant completed six trials (2 devices × 3 brightness modes), with each trial lasting 60 seconds. Eye-tracking events were classified into saccades, fixations, and other categories using Tobii's built-in algorithms.

## Data Preprocessing

- Blinks and tracking errors were flagged as `EyesNotFound` or `Unclassified`
- Pupil diameter values outside physiologically plausible ranges were excluded from analysis
- No interpolation was performed on missing data points
- The dataset represents cleaned and validated records used in the manuscript analyses

## Usage Examples

### Loading the data in Python
```python
