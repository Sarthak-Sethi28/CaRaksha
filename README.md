<div align="center">

# CaRaksha

**A portable road-safety prototype that combines driver monitoring, alcohol detection, overspeed alerts, accident response, and road-condition sensing in one system.**

Originally developed as an engineering project at **Lotus Valley International School, Noida**.

</div>

---

## The problem

Road-safety failures rarely come from a single source. A driver can be distracted, impaired, overspeeding, or involved in a crash where emergency response is delayed.

CaRaksha was designed around a simple idea: instead of building a separate device for each failure mode, combine sensing, driver feedback, location awareness, and emergency communication into one portable system that can work with both newer and older vehicles.

## System overview

```text
                         CaRaksha
                            │
        ┌───────────────────┼────────────────────┐
        │                   │                    │
        ▼                   ▼                    ▼
 driver monitoring     vehicle sensing      environment sensing
 camera / vision       speed / alcohol      road / proximity
        │                   │                    │
        └──────────────┬────┴─────────────┬──────┘
                       ▼                  ▼
                 local alerts        emergency flow
                 buzzer / LCD        GPS + GSM / SOS
```

The prototype combines a Raspberry Pi / Arduino-based hardware stack with cameras, GPS, proximity sensors, an alcohol sensor, local alerts, and communication modules.

## Safety modules

| Module | What it does |
| --- | --- |
| Driver monitoring | Uses a camera-based pipeline to detect signs of distraction or drowsiness and trigger an in-car alert |
| Overspeed prevention | Monitors vehicle speed and warns the driver when a configured threshold is exceeded |
| Alcohol detection | Uses an ethanol sensor to detect alcohol and trigger an alert / emergency workflow |
| Accident response | Surfaces stored medical information and uses location + communication modules to help notify emergency contacts |
| Road-condition mapping | Uses an external camera / processing pipeline to identify road obstacles and poor road conditions |
| Inter-vehicle safety | Explores proximity-based warnings intended to reduce rear-end collisions during sudden braking |

## Hardware + software

**Compute**  
Raspberry Pi · Arduino

**Sensing**  
Camera · GPS · ultrasonic sensors · ethanol sensor

**Feedback + communication**  
Buzzer · LCD · GSM module

**Software**  
Python / computer-vision processing · embedded control logic · sensor integration

## Design goals

### Portable rather than vehicle-specific

The system was conceived as an add-on rather than something that requires a new vehicle platform, making the idea relevant to a much wider range of cars.

### Multiple signals, one safety workflow

Instead of treating driver behaviour, vehicle state, and emergency response as unrelated problems, CaRaksha combines them into a single safety layer.

### Accessible prototype cost

The original prototype estimate was approximately **₹14,000 INR**, including the major sensing and compute components used in the concept.

## Project report

The repository includes the original project documentation with additional context on the concept, components, and design:

**[Read the full CaRaksha project report →](./CaRaksha.pdf)**

## Project context

CaRaksha began as a school engineering project focused on applying embedded systems and computer vision to a real-world safety problem. This repository preserves that prototype and its technical documentation as part of my project history.

> **Prototype note:** CaRaksha is an engineering prototype / concept, not a certified automotive safety device or production emergency-response system.

---

Built by the CaRaksha project team at **Lotus Valley International School, Noida**.  
More of my current software and AI work: **[sethisarthak.com](https://sethisarthak.com)**
