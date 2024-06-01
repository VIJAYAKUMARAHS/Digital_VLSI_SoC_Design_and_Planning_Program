# DIGITAL VLSI SOC DESIGN AND PLANNING 
Hello, everyone! I'll be sharing what I have learned during a 2 weeks of workshop on Digital VLSI SOC design and planning using openLANE tool and sky-130nm PDK under the guidance of Kunal Ghosh, VLSI System Design(VSD) pvt.ltd.

## Day 1 -Inception of open-source EDA, OpenLANE and sky130 PDK

## How to talk to computers
### Introduction to QFN-48 Package, chip, pads, core, die and IPs

ARDUINO BOARD: Lets start with an  arduino board, the encircled area is a microcontroller chip. to design such chip or IC we have to follow the ASCI design flow.
![01 06 2024_19 11 14_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/14c33535-27d0-4951-8e70-422a6fb93d3b)

chip architecture 
![01 06 2024_19 29 15_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a5d5897c-74a0-4c4b-b0e1-cb4186923e32)

Post chip fabrication the chip is in the form of die then we package that die in to required package form.
Package: QFN 48 quad flat No leads
![01 06 2024_19 33 30_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/6d523206-9dd8-483a-861a-b2e638e7c827)

![01 06 2024_19 42 57_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/66f28906-d9da-4952-a27a-f39f96136841)


![01 06 2024_19 45 35_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/e2361841-3394-4612-9fa7-51629326378b)

CORE: Where we place the IPs, Macro and standard cell.

DIE: the size of an entire chip area

PADS: this is where we are giving signal in and take out and also we place protection circuit here. when comes to full chip level design we say pads, when comes to block level design we say ports.

#### Sample SOC look like

![01 06 2024_19 56 09_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/5df9da25-909c-4971-b17b-05eb9599487e)

Foundry: where chip are fabricated.

![01 06 2024_19 59 04_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/b56ea874-f46d-41e6-a27d-a5de449530b7)

Foundry look like (smale setup:IIT Bombay)

![01 06 2024_20 01 22_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/51d5fda1-155a-43b9-ab41-69c40cc3083b)

### Introduction to RISC-V
RISC architecture that were developed at the University of California, Berkeley. RISC is an open standard instruction set architecture (ISA) based on established RISC principles. Unlike most other ISA designs, RISC-V is provided under open source licenses that do not require fees to use. A number of companies are offering or have announced RISC-V hardware, open source operating systems with RISC-V support are available, and the instruction set is supported in several popular software toolchains.
![01 06 2024_20 12 29_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/fdda8d67-121b-4195-9c81-3e3ea5755f87)

![01 06 2024_20 15 52_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/ae32e585-a1df-4cc6-9879-61df378cae9b)

### From Software Applications to Hardware
Application Software - System Software - Hardware chip

Application software are enters into system software and system sodtware converts the entire program into binary language.

*Operating System, Compiler, Assemblers*

Operating system handles input/output operations and allocate memory also it manage the low level system functions.

Compiler takes the output from the operating system as programming languages such as C,C++,Java and convert them into intsructions. These instructions depends upon hardware.

Assembler take the instructions from compiler and convert them into binary numbers. This binary language send to hardware and hardware performs ouput based on the function.

Instruction acts as abstract interface between C-language and the hardware.

![01 06 2024_20 25 44_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a5d78a15-635b-4087-ad1f-7bd743b28e04)

![01 06 2024_20 27 55_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/a1e745b2-cbbd-4693-a3d9-8c1ff2858bac)

![01 06 2024_20 29 25_REC](https://github.com/VIJAYAKUMARAHS/VSD-SoC_Design_and_Planning_Program/assets/89599199/e113f08c-6cdb-47cb-93f2-6b53e86cf77e)

## Soc design and OpenLANE
### Introduction to all components of open-source digital asic design







