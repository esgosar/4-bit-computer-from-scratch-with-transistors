# 💻 4-Bit Transistor Computer from Scratch (RTL Logic)

Welcome to the **4-Bit Discrete Transistor Computer** project! This repository contains the complete hardware design, schematics, and SPICE simulations for a fully functional 4-bit CPU built entirely from individual, discrete Resistor-Transistor Logic (RTL) components—**no integrated circuits (ICs) allowed.**

The entire project is designed, tested, and simulated using **KiCad on macOS**, providing a practical blueprint to bridge the gap between pure semiconductor physics and high-level computer architecture.

---

## 🚀 Execution Plan & Project Roadmap

Building a CPU out of individual transistors requires a modular, step-by-step approach. Below is our roadmap from a single NAND gate to a fully running 4-bit computer.

### 🔳 Phase 1: Logic Gates & Building Blocks (Current Phase)
* [x] Design and simulate a stable RTL **NAND Gate** using NPN transistors.
* [ ] Create universal hardware sub-sheets (Hierarchical Sheets) in KiCad for standard gates: NOT, AND, OR, NOR, XOR.
* [ ] Document and bypass Mac-specific KiCad SPICE simulation bugs.

### 💾 Phase 2: Memory & Registers (Storage)
* [ ] Build a **1-Bit SR Latch** (Memory Cell) by cross-coupling two NAND gates.
* [ ] Design a **D-Type Flip-Flop** synchronized with a system clock.
* [ ] Combine 1-bit cells into a modular **4-Bit Data Register** to hold variables.

### 🧮 Phase 3: Arithmetic Logic Unit (ALU)
* [ ] Design a Half-Adder and a **1-Bit Full Adder** utilizing discrete gates.
* [ ] Cascade four 1-bit adders to create a **4-Bit Parallel Adder** with Carry flags.
* [ ] Implement basic bitwise logical operations (AND, OR, NOT).

### 🕹️ Phase 4: Control Unit & Clock
* [ ] Build an adjustable **System Clock** utilizing a transistor-based astable multivibrator circuit.
* [ ] Design the **Program Counter (PC)** to increment memory addresses sequentially.
* [ ] Create the **Instruction Decoder** matrix to turn binary opcodes into hardware control signals.

### 🔌 Phase 5: Backplane & Daughterboard Integration
* [ ] Establish a modular hardware topology (Daughterboards plugged into a central passive Backplane).
* [ ] Route PCBs in KiCad optimizing for manual hand-soldering.
* [ ] Run hardware-in-the-loop diagnostic tests with test point LEDs.

---

## 🛠️ Chapter 1: The Project's Atom - The RTL NAND Gate

The fundamental building block of our CPU is a NAND gate based on two NPN transistors (e.g., 2N3904). When both inputs receive 5V, the output drops to 0V (Ground). In any other combination, the output remains high at 5V.

### Truth Table (NAND Logic)


| A |  B | Output | Voltage Level |
| :---: | :---: | :---: | :---: |
| 1 | 1 | **0** | Low |
| 0 | 1 | **1** | High |
| 1 | 0 | **1** | High |
| 0 | 0 | **1** | High |

---

## ⚠️ macOS KiCad Simulation Quick-Fixes

If you are simulating this project on a Mac, ensure you follow these two rules to prevent the `ngspice` simulation engine from crashing:

1. **Avoid iCloud Drive Sychronization:** Never run your project folder inside `Desktop` or `Documents` if they sync with iCloud. The virtualized path will cause a reading error. Keep the project directory strictly local (e.g., inside `/Users/your_user/Downloads/` or a custom local folder).
2. **Force Absolute Ground Reference:** Generic ground flags can cause drift during matrix calculations. Place a local **Global Label** named exactly `0` (the number zero) directly onto your main ground net to establish an unyielding 0.0V reference for SPICE.

---

## 🤝 Contributing & License

This project is fully open-source. Feel free to fork the repository, open issues with simulation optimizations, or suggest architectural changes to the roadmap!
