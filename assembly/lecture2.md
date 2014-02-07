# Microcomputer Architecture (Von Neumann/Princeton)

Bit beer == bits

## Arithmetic Logic Unit
The arithmetic logic unit is the brewhouse.

Contains:
- Adder
- Registers

## Controller
Controller is the administration, controls everything.

Bundles of information are buses.

Control bus connects the controller with the ALU.  The control bus is bidirectional.  The controller says, add this, subtract that.  The ALU sends back flags like overflow.

Controller has condition code by control bus, and instruction register by data bus

## Storage/RAM
Random access memory.

Bottles == data

Data bus goes from the RAM to the ALU

Address bus goes from controller EA (effective address) and PC (program counter) to RAM
Read/Write line goes from controller to the RAM to tell it to read or write.



Data bus goes out to I/O, keyboard, monitors, other peripherals.
