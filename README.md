# Line Following Robot

A compact line-following robot designed around an ESP32, N20 geared motors with encoders, and an adjustable analog IR sensor array.

The chassis went through multiple design iterations before settling on a simpler and more practical layout. The main focus was keeping the sensor mounting adjustable, making the electronics easier to mount, and keeping the battery secure without making the chassis unnecessarily complicated.

---

## Components

### Electronic

- **Microcontroller:** ESP32
  - Specific version: __________
- **IR Sensor Array:** Analog straight IR sensor array
- **Motor Driver:** __________
- **Battery:** 2 × 2.7 V Li-ion batteries
- **Battery Holder:** 1 × __________
- **Power Converter / Buck Converter:** __________

### Mechanical

- **Motors:** 2 × N20 6 V geared motors with encoders
- **Wheels:** 2 × high-traction 32 mm wheels
- **Caster Wheel:** 1 × caster ball mount
- **Chassis:** Custom CAD-designed chassis
- **Fasteners:** M2.0 nuts and screws

---

## Chassis

The chassis was designed in two main versions.

### V1 — Curved IR Array Design

![Chassis V1]

The first version was designed around a **curved IR sensor array**. The idea was to place the sensors along a curved front section so the array could cover a wider area while following the line. The chassis also had to accommodate the required sensor mounting holes and spacing.

There were two major problems with this design:

1. **Coding complexity** — A curved sensor arrangement requires more complicated sensor mapping and calibration. Since the sensor positions aren't evenly aligned along a straight line, converting the readings into a reliable position/error value is more difficult.
2. **CAD hole spacing** — Getting the correct hole positions, lengths, and widths for the curved arrangement became a major problem during CAD modelling. Small changes in sensor dimensions or mounting positions affected the rest of the chassis.

After considering these issues, the curved-array design was dropped in favour of a simpler straight sensor arrangement.

### V2 — Straight Analog IR Array (Current)

![Chassis V2]

The second version uses a **straight analog IR sensor array**. This makes the sensor readings easier to process because the sensors are arranged along a single straight line, and it makes physical mounting and calibration much simpler.

**Main changes:**

- Replaced the curved IR array with a straight analog IR array.
- Added a **long straight mounting slot** for the sensor/PCB.
- The slot allows sensor position to be adjusted instead of being fixed.
- Improved the PCB mounting arrangement.
- Added two large rectangular recessed/extruded sections for the battery holder.
- Battery holder sits securely on the chassis instead of shifting during operation.
- Battery holder/PCB can be secured further with mounting screws if needed.

The final layout is intended to make assembly and future changes easier without redesigning the entire chassis.

---

## Chassis Design Features

### Adjustable Sensor Mount

A straight slot is provided for the IR sensor array, allowing it to be moved forward or backward during testing to find the best position for line detection and turning performance.

```text
        IR SENSOR ARRAY
    ─────────────────────
          ↑       ↑
       Adjustable slot
    ─────────────────────

             CHASSIS
```

### Battery Mount

Two large rectangular sections provide a stable location for the battery holder. It can be placed on top of the base and secured with mounting screws if required, preventing the batteries from shifting during sharp turns.

---

## CAD Design

The chassis was designed with emphasis on:

- Simple manufacturability
- Adjustable sensor positioning
- Easy PCB mounting
- Secure battery placement
- Low unnecessary material
- Easy access to electronics
- Compatibility with N20 motors and 32 mm wheels

Final chassis dimensions and hole positions may be adjusted after physical testing, since actual component tolerances can differ from CAD dimensions.

---

## Assembly

1. Mount the two N20 motors to the chassis.
2. Install the 32 mm wheels on the motor shafts.
3. Install the caster ball mount.
4. Mount the ESP32 and motor driver.
5. Install the analog IR sensor array in the adjustable slot.
6. Place the two Li-ion batteries in the battery holder.
7. Secure the battery holder using the provided mounting arrangement.
8. Connect the motors, encoder outputs, IR array, ESP32, motor driver, and power system.
9. Test the sensor position before permanently tightening the mounting screws.

---

## Design Considerations

One of the main problems during the CAD stage was **hole placement and dimensional accuracy**. Since the chassis depends on several different components being mounted together, even a small error in hole spacing or width can cause problems during physical assembly.

For this reason, the V2 design uses slots where adjustment is useful instead of relying on a single fixed mounting position, making the chassis more forgiving during assembly and testing.

---

## Testing Checklist

- Motor mounting hole alignment
- Wheel clearance
- Caster height
- IR sensor height from the track
- IR sensor position relative to the wheels
- Battery holder fit
- PCB mounting holes
- Screw clearance
- Cable routing
- Overall chassis balance

---

## Future Improvements

- Finalising the exact ESP32 variant
- Finalising the motor driver
- Improving PCB mounting
- Adding dedicated cable-routing holes
- Reducing unnecessary chassis material
- Adding more adjustable mounting points
- Testing different IR sensor positions
- Optimising the chassis after the first physical prototype

---

## Repository Structure

```text
.
├── Cad/
│   ├── Bracket.SLDPRT
│   ├── Caster_Ball_Mount.SLDPRT
│   ├── Chasis.SLDPRT
│   └── Chasis_final.SLDPRT
├── Docs/
│   └── Components/
├── Firmware/
├── BUILDLOG.md
└── README.md
```

---

## Current Status

| Part | Status |
|---|---|
| N20 6 V Motors | Selected |
| ESP32 | Selected — version TBD |
| Motor Driver | TBD |
| IR Sensor | Straight analog array |
| Battery | 2 × Li-ion |
| Battery Holder | Selected |
| Wheels | Selected |
| Chassis V1 | Abandoned |
| Chassis V2 | Current design (`Chasis_final.SLDPRT`) |
| PCB Mounting | Improved |
| Adjustable IR Mount | Added |
| Battery Mount | Added |

---

## Notes

This chassis is still a prototype. Final dimensions may change after testing the actual motors, wheels, sensor array, battery holder, and electronics together.

The main goal of the current design is to keep the robot simple, adjustable, and easy to modify while avoiding the mounting and CAD issues encountered in V1.
</content>
# Testrig
First rmi project 
