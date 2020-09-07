# dramduino_16k
## Memory tester for 4116 compatible 16k DRAM chips

This repository contains a modified version of the "DRAMduino" code that's floating around several retro computer forums; the original source of this code appears to be here:

https://forum.defence-force.org/viewtopic.php?p=15035

This version has been modified for the 7-bit RAS/CAS addresses of the smaller 16k chips; the code to select chip size has been removed, although it could be restored if you wanted to add support for other chips with compatible voltage requirements, like the older MK4027/4096 4K DRAMs.

This code should work on any regular Arduino, but has only been tested on a knockoff Arduino Nano board. The pin designations in the original code have been redone to match the current numbering scheme in the Arduino IDE, and are arranged to facilitate straight-across wiring between the Nano package and a 4116 on a breadboard. Connect as follows (view text in raw format):

           4116
        +-------+
  -5v --|1    16|-- GND
  A0  --|2    15|-- D8
  A1  --|3    14|-- D7
  A3  --|4    13|-- D6
  A4  --|5    12|-- D5
  A5  --|6    11|-- D4
  A6  --|7    10|-- D3
 +12v --|8     9|-- +5v
        +-------+
       
 +5v -- Red LED -- 470 ohm resistor --- D11
 +5v -- Green LED -- 470 ohm resistor - D12
       
Power may be tapped off an ATX power supply; connect a small resistive load (~5w) across +5v and ground, and tap the needed voltages from their respective pins. If you're driving the Arduino off of USB you don't need to power the Arduino with the +5v line, but connect the ground pin to the same common used by the PSU and GND on the 4116. Short the ATX power control pin to ground to start. If the Arduino is booted before the power supply is on, hit the reset button to begin test.
