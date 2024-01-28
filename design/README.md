## A dual-cpu SBC

Design scratch...

Provide me a schematic for a dual-cpu 6809 single-board computer with 62256 RAM, 27C256 ROM, and a 6850 UART.

Here's an example schematic for a dual-CPU 6809 single-board computer with 62256 RAM, 27C256 ROM, and a 6850 UART:

```
+------------------+
| 6809 CPU (Master) |
+------------------+
| 6809 CPU (Slave)  |
+------------------+
| 62256 RAM (64K)  |
+------------------+
| 27C256 ROM (32K) |
+------------------+
| 6850 UART        |
+------------------+
```

Here's a more detailed breakdown of the schematic:

### CPU Connections

Each 6809 CPU is connected to the following buses:

* **Address bus:** This bus is used to select a memory location or I/O device.
* **Data bus:** This bus is used to transfer data between the CPU and memory or I/O devices.
* **Control bus:** This bus is used to send control signals to memory or I/O devices.

The two CPUs share the same address bus, data bus, and control bus. This means that they can both access the same memory and I/O devices at the same time. However, the CPUs can use different memory locations and I/O ports, so they can operate independently of each other.

### RAM Connection

The 62256 RAM is connected to the address bus, data bus, and control bus. The RAM is organized as a 64K x 8 byte memory space. This means that it can store up to 64,000 bytes of data.

### ROM Connection

The 27C256 ROM is also connected to the address bus, data bus, and control bus. The ROM is organized as a 32K x 8 byte memory space. This means that it can store up to 32,000 bytes of data. The ROM typically contains the boot code for the computer.

### UART Connection

The 6850 UART is connected to the data bus, control bus, and a serial port. The UART is used to communicate with external devices, such as a terminal or modem.

### Interrupt Handling

The two CPUs can share the same interrupt system. This means that they can both receive interrupts from external devices. The interrupt system is responsible for determining which CPU should handle a particular interrupt.

### Power Supply

The computer requires a power supply to provide power to the CPUs, RAM, ROM, and UART. The power supply typically outputs +5V and +12V.

This is just a basic schematic for a dual-CPU 6809 single-board computer. There are many different ways to implement this design, and the specific components used will depend on the desired performance and features. Here's a block diagram for a dual-CPU 6809 single-board computer with 62256 RAM, 27C256 ROM, and a 6850 UART:

```
    +---------------------+
    |   Dual 6809 CPU      |
    |                       |
    |      Address Bus      |
    |                     ---|
    |     Data Bus         |
    |                     ---|
    |  Control Bus         |
    |                     ---|
    |                       |
    +---------------------+
    |   62256 RAM         |
    |                       |
    |   62256 RAM         |
    |                       |
    +---------------------+
    |   27C256 ROM       |
    |                       |
    +---------------------+
    |   6850 UART       |
    |                       |
    |   RS-232 Interface    |
    |                       |
    +---------------------+
```

Here's a more detailed schematic of the CPU logic:

```
    +---------------------+
    |   6809 CPU         |
    |      Address Bus      |
    |                     ---|
    |     MPU Control      |
    |                     ---|
    |   PIA Interface     |
    |                     ---|
    |                       |
    +---------------------+
    |   6809 CPU         |
    |      Address Bus      |
    |                     ---|
    |     MPU Control      |
    |                     ---|
    |   PIA Interface     |
    |                     ---|
    |                       |
    +---------------------+
```

The PIA (Programmable Interface Adapter) is used to communicate between the CPUs and the external devices. The PIAs can be used to control the RAM, the ROM, and the UART.

Here's a schematic of the RAM:

```
    +---------------------+
    |   62256 RAM         |
    |      Address Bus      |
    |                     ---|
    |     Data Bus         |
    |                     ---|
    |       Control       |
    |                     ---|
    +---------------------+
```

The RAM can be used to store programs and data.

Here's a schematic of the ROM:

```
    +---------------------+
    |   27C256 ROM       |
    |      Address Bus      |
    |                     ---|
    |     Data Bus         |
    |                     ---|
    |       Control       |
    |                     ---|
    +---------------------+
```

The ROM can be used to store firmware.

Here's a schematic of the UART:

```
    +---------------------+
    |   6850 UART       |
    |      Address Bus      |
    |                     ---|
    |     Transmit Data    |
    |                     ---|
    |     Receive Data     |
    |                     ---|
    |     Control         |
    |                     ---|
    +---------------------+
```

The UART is used to communicate with other devices over a serial port.

This is just a basic schematic, and there may be other components that you need to add depending on your specific application.

### Drawing details

Here is a possible EasyEDA board layout for a dual-CPU 6809 single-board computer with 62256 RAM, 27C256 ROM, and a 6850 UART:

**Components**

* 1x 6809 CPU (Motorola)

* 2x 62256 RAM (256K x 8-bit SRAM)

* 1x 27C256 ROM (32K x 8-bit ROM)

* 1x 6850 UART (asynchronous serial interface)

* 1x power supply

**Connections**

* CPU1:
    * A0-A7: 62256 RAM (MISO)
    * D0-D7: 62256 RAM (MOSI)
    * R/W: 62256 RAM (/CS)
    * E: 62256 RAM (/WE)
    * CLK: system clock
    * HLDA: 6850 UART (SOUT)

* CPU2:
    * A0-A7: 62256 RAM (MOSI)
    * D0-D7: 62256 RAM (MISO)
    * R/W: 62256 RAM (/CS)
    * E: 62256 RAM (/WE)
    * CLK: system clock
    * HALT: 6850 UART (SOUT)

* 62256 RAM:
    * MISO: CPU1 (A0-A7)
    * MOSI: CPU2 (D0-D7)
    * /CS: CPU1 (R/W)
    * /WE: CPU1 (E)

* 27C256 ROM:
    * D0-D7: CPU1 (A0-A7)
    * CS: CPU1 (R/W)
    * /OE: CPU1 (E)

* 6850 UART:
    * TX: CPU1 (HLDA)
    * RX: CPU2 (HALT)
    * /CTS: CPU1 (A8)
    * /RTS: CPU2 (A8)

* Power supply:
    * +5V: CPU1, CPU2, 62256 RAM, 27C256 ROM, 6850 UART
    * GND: all components

**Layout**

The board should be laid out as follows:

* Place the CPU1 and CPU2 chips on opposite sides of the board.

* Place the 62256 RAM chips and 27C256 ROM chip in the center of the board.

* Place the 6850 UART chip near the CPU1 chip.

* Connect the components as shown in the connections table.

**Additional notes**

* The board should be designed to be double-sided.

* The components should be spaced as far apart as possible to minimize crosstalk.

* The power supply should be routed to the components that need it.

* The ground plane should be as large as possible to reduce noise.

I hope this helps!