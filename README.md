# dramduino_16k
## Memory tester for 4116 compatible 16k DRAM chips

This repository contains a modified version of the "DRAMduino" code that's floating around several retro computer forums; the original source of this code appears to be here:

https://forum.defence-force.org/viewtopic.php?p=15035

This version has been modified for the 7-bit RAS/CAS addresses of the smaller 16k chips; the code to select chip size has been removed, although it could be restored if you wanted to add support for other chips with compatible voltage requirements, like the older MK4027/4096 4K DRAMs.
