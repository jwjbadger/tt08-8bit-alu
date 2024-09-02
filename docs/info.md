<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project currently works by including a 8-bit shift register connected to the bus. The bus is a conjunction of OR-gates making it one directional (as simply combining the wires seems less possible). There is a tri-state buffer that connects to two registers (register A and B) allowing them to interact with the bus. The direction is controlled using DIRA and DIRB. If the DIRA/DIRB sets the direction to be using the bus as an input, LA/LB determines whether the register should load what is on the bus. Currently Register A and Register B are directly connected to the ALU, but in the future Register B will be directly connected and the other input will be the bus. 

## How to test

Input your two numbers MSB first, pulsing the clock after inputting each individual bit. Use OS to determine whether the shift-register will output to the bus. Leave DIRA and DIRB on their default to allow information to stream in from the bus. Set LA or LB appropriately depending on where you would like to load information. Pulse the clock and reset LA/LB to load the information in the bus. Whenever Register A and B are set correctly, the output will be produced automatically. The output will be produced with OUT0 indicating the LSB and OUT7 indicating the MSB.

## External hardware

A sequence of 8 LEDs is hooked up to the outputs to display the final number in binary.
