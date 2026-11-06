# Automatic Driver Assistance System (Arduino)

A low-cost Arduino UNO system that automates headlight switching and in-cabin air circulation based on environmental conditions.

## What it does
- **Headlights:** an LDR (light sensor) switches the LED headlights between low and high beam depending on ambient light.
- **Air quality:** an MQ-135 gas/smog sensor turns on a DC cooling fan through a relay when the reading passes a threshold (about 400).
- **Rain:** a rain sensor detects wet conditions for logging or alerts (designed to be extended).
- Sensor readings are visible in the Arduino Serial Monitor.

## Hardware
Arduino UNO, LDR, rain sensor (MH-RD), MQ-135 gas sensor, 2-channel relay module, DC fan, LED lights, breadboard/perfboard and jumper wires.

See `images/` for the built prototype.

## Code
`src/driver_assistance.ino` is a **reconstruction** of the sketch, written from the project report after the original file was lost. Pin numbers and thresholds are defaults, so change the constants at the top to match your wiring and calibrate the sensors. Relays are assumed active-LOW.

## Logic (if/else on sensor thresholds)
| Condition | Action |
|---|---|
| LDR value low (dark) | LED headlights ON |
| LDR value high (bright) | LED headlights OFF |
| MQ-135 above threshold | Cooling fan ON |
| Rain detected | Log / alert |

## Possible applications
Aftermarket safety upgrade for budget vehicles, e-bikes, smart helmets, industrial vehicles.

## Limitations
Basic sensors only, needs manual threshold calibration, not weatherproof.

## Tech
Arduino (C/C++), sensors and relays, circuit design, embedded systems

## Team (Digital Design course, Bahria University Islamabad)
Ayan Aqeel — circuit design and testing · Hamza Sheikh — coding and sensor integration · Abdul Rehman — documentation and presentation
