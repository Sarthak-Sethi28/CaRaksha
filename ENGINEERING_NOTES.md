# Engineering Notes

This document captures the prototype architecture, boundaries, and realistic next steps for CaRaksha.

## System boundaries

CaRaksha combines several independent safety signals into one prototype workflow:

- driver-state signals from camera / vision processing
- vehicle-state signals such as speed and alcohol sensing
- proximity and road-environment signals
- local driver feedback through buzzer / display
- emergency communication through GPS + GSM

Each module should fail independently rather than taking down the entire system. A sensor failure should degrade one capability, not disable every safety function.

## Prototype signal flow

```text
sensor input
   │
   ▼
validation / preprocessing
   │
   ▼
module-level decision
   │
   ├──► local driver alert
   │
   └──► emergency / communication flow when required
```

## Important limitations

This repository represents an engineering prototype, not a certified automotive product. Before any real deployment, the system would require substantial validation around sensor accuracy, false positives, environmental conditions, power reliability, communication failures, privacy, and automotive safety standards.

## Sensible next steps

1. Separate each safety feature into a testable module with defined inputs and outputs.
2. Add recorded sensor fixtures so the software can be tested without physical hardware attached.
3. Measure false-positive / false-negative rates for driver monitoring and road-condition detection.
4. Add timeout and fallback behaviour for GPS, GSM, and sensor failures.
5. Define a clear event model for when local alerts escalate into emergency notifications.
6. Run controlled hardware-in-the-loop tests before considering any real vehicle trial.

These notes are intentionally conservative: the goal is to preserve the original prototype while making its engineering assumptions and limitations explicit.
