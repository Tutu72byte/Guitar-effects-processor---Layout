# Musical Effects Processor - TIE2026 PCB Design Contest

## General Description

Complete PCB Design of an embedded music signal processing module (Guitar Effect Pedal) from block diagram to circuit schematic, layout and generation of manufacturing files using KiCad. The projects consists of:

* 1) Library Creation: Created dedicated project libraries (TIE2026.kicad_sym and TIE2026.pretty) containing custom schematic symbols and footprints.

* 2) Schematic design: The circuit diagram contains a Microcontroller, SPI Flash Memory, ADC/DAC audio processing stages,
   an interactive touchscreen interface and a switching power supply (9V in, 5V and 3.3V converters and regulators and a 2.5V bias).
   Incorporated specific JTAG and power rail test pads for hardware debugging.

* 3) PCB Topology & Stack-up(Configured a 4-layer board stack-up (1.6mm total thickness)):

  * **Layer 1 (Top):** Primary component placement and routing layer, high-speed signals (SPI, I2C for JTAG).
  * **Layer 2 (Inner 1 - AGND and GND):** A split internal ground plane for both the analog and digital circuits, linked via the 10m-Ohms shunt R28, isolating the delicate analog circuitry from the fast paced, high slew rate digital signals.
  * **Layer 3 (Inner 2 - Power Plane):** Split power planes dedicated to distributing various supply voltages (+5V, +3.3V) cleanly across the board.
  * **Layer 4 (Bottom):** Secondary routing layer and test-point placement.
* **High-Speed Routing:** Differential pairs (for the MOLEX screen) were routed with controlled impedance and matched lengths to preserve signal integrity (Within the limits of the footprints and pads dimensions).
* **Component Placement & Decoupling:** 
  * All decoupling capacitors were placed as close as possible to the power pins of their respective ICs to minimize parasitic inductance and noise (Especially on the bottom right of the board where the converter sits).
  * Quartz crystal oscillators were positioned directly adjacent to their target chips to ensure clean clock generation.
* **Test Points:** Dedicated test points  were strategically placed on the board to facilitate hardware debugging, signal probing, and manufacturing verification.

4) Routing for High-Speed Signals & Impedance Control: Implemented single-ended 50 Ohms data lines for the Flash memory and 100 Ohms differential lines for the video interface.

5) Manufacturing Output: Generated industry-standard production packages, including extended
   Gerber files, Drill files, a Pick-and-Place component file and a Bill of Materials (BOM).
