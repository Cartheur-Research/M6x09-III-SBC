## The EasyEDA layout

Here is an EasyEDA board layout for a dual-CPU 6809 single-board computer with 62256 RAM, 27C256 ROM, and a 6850 UART:

**Board Dimensions:** 100mm x 100mm
**Board Layers:** 2 layers (top and bottom)
**Footprints:**
* 2x 6809 CPU
* 2x 62256 RAM
* 2x 27C256 ROM
* 1x 6850 UART
* 1x USB connector
* 1x power jack
* 1x reset button
* 1x LED
* 1x 32-pin header

**Connections:**
* CPU 1:
    * Address bus: D0-D15
    * Data bus: D0-D7
    * Control bus: CLK, MREQ, WR, RD, IORQ, HLDA, RESET, NMI, IRQ, FIRQ
* CPU 2:
    * Address bus: D16-D31
    * Data bus: D8-D15
    * Control bus: CLK, MREQ, WR, RD, IORQ, HLDA, RESET, NMI, IRQ, FIRQ
* RAM 1:
    * Address bus: D0-D15
    * Data bus: D0-D7
* RAM 2:
    * Address bus: D16-D31
    * Data bus: D8-D15
* ROM 1:
    * Address bus: D0-D15
    * Data bus: D0-D7
* ROM 2:
    * Address bus: D16-D31
    * Data bus: D8-D15
* UART:
    * TxD: P2-0
    * RxD: P2-1
    * RTS: P2-2
    * CTS: P2-3
* USB:
    * D+: P0-0
    * D-: P0-1
* Power:
    * VCC: P1-0
    * GND: P1-1
* Reset:
    * RESET: P3-0
* LED:
    * LED: P3-1
* Header:
    * P0-4 to P0-15
    * P1-2 to P1-23
    * P2-4 to P2-31
    * P3-2 to P3-23

This board layout provides a basic foundation for a dual-CPU 6809 single-board computer. With careful planning and design, it can be expanded to include additional features such as more RAM, ROM, and I/O ports. 

### Conditions to be applied here

While I can't physically draw a board layout, I can provide you with a detailed description of the layout and the component placement.

**Board Layout Overview**

The board layout for the dual-cpu 6809 single-board computer will be a standard double-sided PCB with dimensions of 100mm x 100mm. The components will be placed on both sides of the board, with the CPU, RAM, and ROM on the top side and the UART and other supporting components on the bottom side.

**Component Placement**

* **Top Side:**
    * CPU: Place the two 6809 CPUs in opposite corners of the board.
    * RAM: Place the two 62256 RAM chips in the center of the board, with one chip aligned with each CPU.
    * ROM: Place the 27C256 ROM chip in the center of the board, between the two RAM chips.

* **Bottom Side:**
    * UART: Place the 6850 UART chip near the edge of the board, on the opposite side from the CPU and RAM.
    * Power Supply: Place the power supply components, including the voltage regulators, capacitors, and inductors, in a separate area of the board.
    * Other Supporting Components: Place other supporting components, such as the reset button, status LEDs, and mounting holes, as needed.

**Component Connections**

* **CPU Connections:** Connect the CPU pins to the RAM, ROM, and UART using ribbon cables or wire jumpers.
* **RAM Connections:** Connect the RAM pins to the CPU using ribbon cables or wire jumpers.
* **ROM Connections:** Connect the ROM pins to the CPU using ribbon cables or wire jumpers.
* **UART Connections:** Connect the UART pins to the CPU, using ribbon cables or wire jumpers.
* **Power Supply Connections:** Connect the power supply components to the board using the appropriate wires and connectors.

**Additional Considerations**

* **Trace Routing:** Route the traces on the board carefully to ensure that they are of adequate width and length for the signal levels and currents of the components.
* **Ground Planes:** Establish ground planes on both sides of the board to provide a low-impedance ground reference for the components.
* **Decoupling Capacitors:** Place decoupling capacitors close to the power pins of the CPU, RAM, and ROM to filter out noise and improve the stability of the power supply.

By following these guidelines, you can create a well-designed PCB layout for the dual-cpu 6809 single-board computer.

### The file looks something like:

```
[Schematic]

NET "A0" LOC = U8   | IOSTANDARD = LVCMOS33;
NET "A1" LOC = U7   | IOSTANDARD = LVCMOS33;
NET "A2" LOC = T22  | IOSTANDARD = LVCMOS33;
NET "A3" LOC = R22  | IOSTANDARD = LVCMOS33;
NET "A4" LOC = P21  | IOSTANDARD = LVCMOS33;
NET "A5" LOC = N19  | IOSTANDARD = LVCMOS33;
NET "A6" LOC = G19  | IOSTANDARD = LVCMOS33;
NET "A7" LOC = H20  | IOSTANDARD = LVCMOS33;

NET "A8" LOC = R21  | IOSTANDARD = LVCMOS33;
NET "A9" LOC = N20  | IOSTANDARD = LVCMOS33;
NET "A10" LOC = T19  | IOSTANDARD = LVCMOS33;
NET "A11" LOC = R19  | IOSTANDARD = LVCMOS33;
NET "A12" LOC = P18  | IOSTANDARD = LVCMOS33;
NET "A13" LOC = T18  | IOSTANDARD = LVCMOS33;
NET "A14" LOC = U19  | IOSTANDARD = LVCMOS33;
NET "A15" LOC = V18  | IOSTANDARD = LVCMOS33;

NET "D0" LOC = T9  | IOSTANDARD = LVCMOS33;
NET "D1" LOC = U8   | IOSTANDARD = LVCMOS33;
NET "D2" LOC = T8  | IOSTANDARD = LVCMOS33;
NET "D3" LOC = R8   | IOSTANDARD = LVCMOS33;
NET "D4" LOC = P7  | IOSTANDARD = LVCMOS33;
NET "D5" LOC = N6  | IOSTANDARD = LVCMOS33;
NET "D6" LOC = M7  | IOSTANDARD = LVCMOS33;
NET "D7" LOC = L6  | IOSTANDARD = LVCMOS33;

NET "R/W" LOC = N4  | IOSTANDARD = LVCMOS33;
NET "CS" LOC = N7  | IOSTANDARD = LVCMOS33;
NET "BUSACK" LOC = P8  | IOSTANDARD = LVCMOS33;

NET "RESET" LOC = P13 | IOSTANDARD = LVCMOS33;
NET "CLK" LOC = C12  | IOSTANDARD = LVCMOS33;

[Board]

Components:
- 2x 6809
- 1x 62256 RAM
- 1x 27C256 ROM
- 1x 6850 UART

Dimensions:
100mm x 100mm
```

This is just a starting point, and you will need to adjust the layout as needed for your specific components and design requirements.