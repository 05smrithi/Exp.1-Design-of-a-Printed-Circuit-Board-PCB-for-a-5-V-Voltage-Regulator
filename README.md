# 🔌 5 V Voltage Regulator PCB Design using KiCad

<p align="center">
  <img src="https://img.shields.io/badge/KiCad-8.0%2B-blue?style=for-the-badge&logo=kicad" alt="KiCad">
  <img src="https://img.shields.io/badge/PCB-Design-green?style=for-the-badge" alt="PCB Design">
  <img src="https://img.shields.io/badge/Regulator-L7805-orange?style=for-the-badge" alt="7805">
</p>

<p align="center">
  <b>Design and development of a 5 V linear voltage regulator PCB using KiCad</b>
</p>

---

## 📌 Project Overview

This project demonstrates the complete **PCB design workflow of a 5 V voltage regulator circuit using KiCad**.

A **7805 linear voltage regulator** is used to regulate a **7–12 V DC input** to a stable **5 V DC output**. The design includes input and output filtering capacitors, an LED power indicator, connectors, PCB routing, copper filling, and design-rule verification.

The project covers the complete process from **schematic capture to PCB fabrication file generation**.

### 🔄 Design Flow

```text
Circuit Design
      ↓
Schematic Capture
      ↓
Electrical Rule Check (ERC)
      ↓
Footprint Assignment
      ↓
PCB Layout
      ↓
Design Rule Check (DRC)
      ↓
3D PCB Verification
      ↓
Gerber & Drill File Generation
```

---

## 🎯 Aim

To design the **schematic and PCB layout of a 5 V voltage regulator circuit using KiCad**, perform **Electrical Rule Check (ERC)** and **Design Rule Check (DRC)**, verify the PCB in 3D, and generate **Gerber and drill files** required for PCB fabrication.

---

## 🧰 Apparatus / Software & Components Required

### Software

| S. No. | Requirement                |
| :----: | -------------------------- |
|    1   | Computer                   |
|    2   | KiCad Version 8.0 or later |
|    3   | KiCad PCB design libraries |

### Components

| S. No. | Component              | Specification      |
| :----: | ---------------------- | ------------------ |
|    1   | Voltage Regulator      | 7805, TO-220       |
|    2   | DC Input Connector     | 7–12 V DC          |
|    3   | Output Connector       | 5 V DC             |
|    4   | Input Capacitor        | 0.33 µF            |
|    5   | Output Capacitor       | 0.1 µF             |
|    6   | Electrolytic Capacitor | 10 µF *(Optional)* |
|    7   | LED                    | Power indicator    |
|    8   | Resistor               | 330 Ω              |

---

## ⚡ Circuit Description

The circuit uses a **7805 linear voltage regulator** to convert the input DC voltage into a regulated **+5 V output**.

The basic operation is:

```text
7–12 V DC Input
       │
       ▼
 ┌──────────────┐
 │ Input Filter │
 │   0.33 µF    │
 └──────┬───────┘
        │
        ▼
 ┌──────────────┐
 │    7805      │
 │   Regulator  │
 └──────┬───────┘
        │
        ├──────────────► +5 V Output
        │
        ▼
 ┌──────────────┐
 │ Output Filter│
 │   0.1 µF     │
 └──────────────┘

        +5 V
          │
       330 Ω
          │
         LED
          │
         GND
```

The **330 Ω resistor and LED** provide a visual indication that the regulated output is available.

---

## 📐 Circuit Schematic

The schematic was created in **KiCad Schematic Editor** using the required components and appropriate net connections.

<p align="center">
  <img width="1917" height="1078" alt="Screenshot 2026-07-27 162300" src="https://github.com/user-attachments/assets/29337470-a377-4e75-9555-230bb25e77b5" />

</p>


---

## 🛠️ Design Procedure

### 1. Create a New KiCad Project

* Open KiCad.
* Create a new project.
* Select an appropriate project directory.
* Open the **Schematic Editor**.

### 2. Draw the Schematic

Place and connect the following components:

* 7805 voltage regulator
* DC input connector
* Output connector
* 0.33 µF input capacitor
* 0.1 µF output capacitor
* Optional 10 µF electrolytic capacitor
* LED
* 330 Ω resistor
* Ground symbols

### 3. Assign Net Labels

The major electrical nets are labelled as:

* `VIN` — Input supply
* `+5V` — Regulated output
* `GND` — Ground

### 4. Perform Electrical Rule Check (ERC)

Run the **Electrical Rule Checker (ERC)** in KiCad.

Any reported electrical issues are examined and corrected before proceeding to PCB layout.

### 5. Assign Footprints

Suitable physical footprints are assigned to all schematic components.

For example:

* 7805 → TO-220 package
* Resistor → Through-hole or suitable SMD footprint
* LED → Appropriate LED footprint
* Capacitors → Suitable capacitor footprints
* Connectors → Appropriate terminal/header footprints

### 6. Transfer the Design to PCB Editor

Open the **PCB Editor** and update the PCB from the schematic.

All components and their corresponding net connections are imported into the PCB layout.

### 7. Component Placement

Components are arranged considering:

* Short and efficient signal paths
* Minimum unnecessary track length
* Ease of assembly
* Thermal considerations for the 7805
* Accessibility of input/output connectors
* Proper placement of filtering capacitors

### 8. Define the Board Outline

A suitable PCB board outline is created using the **Edge.Cuts** layer.

### 9. Route PCB Tracks

The electrical connections are routed according to the schematic.

Appropriate track widths and clearances are maintained based on the design requirements.

### 10. Create the Ground Plane

A copper zone is created and connected to **GND** to provide a low-impedance return path and improve the overall PCB layout.

### 11. Run Design Rule Check (DRC)

The **Design Rule Checker (DRC)** is executed to identify:

* Clearance violations
* Unconnected nets
* Track-width violations
* Board-edge violations
* Other PCB design-rule errors

All reported violations are corrected before finalizing the board.

### 12. Add PCB Information

The final PCB includes relevant design information such as:

* Component reference designators
* Board title
* Revision information
* Other required silkscreen markings

### 13. Generate Fabrication Files

Finally, the required manufacturing files are generated:

* **Gerber files**
* **Drill files**

These files can be provided to a PCB manufacturer for fabrication.

---

## 🖥️ PCB Layout

The completed PCB layout contains the placed components, routed tracks, board outline, silkscreen information, and copper ground plane.

<p align="center">
 <img width="1917" height="1078" alt="Screenshot 2026-07-27 162309" src="https://github.com/user-attachments/assets/01537689-58d5-4e48-b2a3-91100abfc4c2" />

</p>

---

## 🧊 3D PCB View

The completed PCB was also inspected using KiCad's **3D Viewer** to verify component placement, board dimensions, and overall physical appearance.

<p align="center">
  <img width="1915" height="1075" alt="Screenshot 2026-07-27 162326" src="https://github.com/user-attachments/assets/b7e0a11d-acc6-4afd-a761-4a67a6582651" />

</p>

---

## ✅ Design Verification

The design was verified using KiCad's built-in electrical and PCB design checks.

| Verification                |    Status   |
| --------------------------- | :---------: |
| Schematic Design            | ✅ Completed |
| Electrical Rule Check (ERC) |   ✅ Passed  |
| Footprint Assignment        | ✅ Completed |
| PCB Layout                  | ✅ Completed |
| PCB Routing                 | ✅ Completed |
| Ground Plane                | ✅ Completed |
| Design Rule Check (DRC)     |   ✅ Passed  |
| 3D PCB Verification         | ✅ Completed |
| Gerber Generation           | ✅ Completed |
| Drill File Generation       | ✅ Completed |

---


## 🏁 Result

The **5 V voltage regulator PCB** was successfully designed using KiCad.

The schematic was verified using **Electrical Rule Check (ERC)**, while the completed PCB layout was verified using **Design Rule Check (DRC)**. The PCB was also inspected using the **3D Viewer** to verify the physical arrangement of components.

Finally, the required **Gerber and drill files** were generated for PCB fabrication.

---

## 📚 Learning Outcomes

Through this project, the following PCB design skills were developed:

* Schematic capture using KiCad
* Component and footprint selection
* Net labelling and electrical connectivity
* Electrical Rule Checking (ERC)
* PCB component placement
* PCB routing
* Ground-plane creation
* Design Rule Checking (DRC)
* 3D PCB visualization
* Gerber generation
* Drill-file generation
* Basic PCB fabrication workflow

---

