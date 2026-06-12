# 💻 4-Bit Discrete Transistor Computer from Scratch (RTL Logic)

A complete hardware architecture design, schematic layout, and SPICE verification of a modular 4-bit CPU synthesized entirely from discrete Resistor-Transistor Logic (RTL) semiconductor elements. This repository bypasses commercial integrated circuits (ICs) to build standard computing primitives directly from individual NPN transistors.

---

## 🛠️ The Problem it Resolves

Modern hardware design abstractions distance engineers from physical computing realities. Most introductory tutorials use monolithic ICs (like the 7400 series) or target FPGA synthesis via HDL, masking complex low-level constraints like **junction saturation delays, switching thresholds, static power dissipation, and load matching (fan-out)**. 

This project bridges the gap between pure semiconductor physics and microarchitecture. It acts as an open-source, step-by-step engineering blueprint optimized for **macOS-based KiCad workflows**.

---

## ⚙️ Installation & Workspace Setup

To clone and configure the simulation environment on your local system (optimized for macOS):

1. **Prerequisites:** Install [KiCad 8.0+](https://kicad.org) (includes native `ngspice` binaries).
2. **Clone the Repository:** Open your terminal and clone the project to a local directory independent of virtual layers (do not use paths actively synced by Apple's iCloud Drive daemon):
   ```bash
   cd ~/Downloads
   git clone https://github.com](https://github.com/esgosar/4-bit-computer-from-scratch-with-transistors
   cd 4-bit-transistor-computer
   ```

---

## 🚀 Usage & Simulation Execution

To verify the operation of Chapter 1's hardware module (**The Universal RTL NAND Gate**):

1. Launch KiCad and open the project file: `NAND-Gate/NAND-Gate.kicad_pro`.
2. Open the schematic sheet: `NAND-Gate.kicad_sch`.
3. In the top window navigation menu, go to **Inspect** $\rightarrow$ **Simulator...**
4. Click on the pre-configured **Transient Analysis Tab** (Transient Sweep, Step: `1u`, Final Time: `4m`).
5. Click the blue **Run (Play)** button in the top toolbar.
6. Select the voltage probe tool and click the target nets `A`, `B`, and `Output` to render the asynchronous timing waveforms.

---
## 📖 Project Documentation & Academic Reports

Detailed hardware specifications, propagation delay analyses, and semiconductor formulation matrices are compiled into formal engineering reports utilizing LaTeX. 

* **Chapter 1 Technical Report (PDF):** You can read the compiled, publication-grade manual directly inside the repository at [`4-bit-computer-from-scratch-with-transistors/documentation/chapter1_nand.pdf`](4-bit-computer-from-scratch-with-transistors/documentation/chapter1_nand.pdf).
* **LaTeX Source Code:** The raw typesetting architecture is available at [`4-bit-computer-from-scratch-with-transistors/documentation/chapter1_nand.tex`](4-bit-computer-from-scratch-with-transistors/documentation/chapter1_nand.tex) for open peer review.

---

## 🤝 Contributing Guide: Building a Computer Engineering Library

This project is not just a static 4-bit CPU; it is designed as a **modular open-source hardware library** for Computer Engineering education. The system utilizes a standardized bus and signal interface so that anyone can design, simulate, and plug in custom logic modules.

We encourage contributors to expand this ecosystem. For example, if the core architecture includes a `4-Bit Parallel Adder`, you can contribute by designing a drop-in `4-Bit Subtractor`, a `Barrel Shifter`, or an `ALU Status Register`.

### Hardware Integration Rules for Custom Modules:
1. **RTL/DTL Constraints:** All logic must be synthesized using discrete transistors and resistors (no monolithic ICs).
2. **Signal Standardization:** Input and output ports must comply with the 5V CMOS/TTL logic level constraints established in our main bus specification.
3. **Hierarchical Modularity:** Encapsulate your circuit into a single KiCad Hierarchical Sheet so users can easily import your module into their top-level CPU designs.
4. **SPICE Validation:** Every submission must include a functional transient simulation testbench inside the project folder.

### How to Contribute:
1. **Fork** this repository.
2. Create your module branch: `git checkout -b feature/4-bit-subtractor`.
3. Commit your KiCad files and your updated local documentation.
4. Open a **Pull Request** detailing your hardware's truth table and transient switching benchmarks.

---

## 📄 License & Contact

* **License:** Distributed under the permissive MIT License. See `LICENSE` for details.
* **Project Maintainer:** esgosar
* **Inquiries & Collaborative Research:** Contact via GitHub Issues or email directly through your profile metadata.
