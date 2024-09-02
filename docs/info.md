<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project currently works by including a 8-bit shift register connected to the bus. The bus is a conjunction of OR-gates making it one directional (as simply combining the wires seems less possible). There is a tri-state buffer that connects to two registers (register A and B) allowing them to interact with the bus. The direction is controlled using DIRA and DIRB. If the DIRA/DIRB sets the direction to be using the bus as an input, LA/LB determines whether the register should load what is on the bus. Register B is connected to the ALU and may be inverted to form a 2's Compliment substraction using the AS pin. The ALU will thus perform addition or subtraction depending on the state of AS. It will take Register A as the other input and output to the bus if the EO pin is pulled high.

## How to test

Input your two numbers MSB first, pulsing the clock after inputting each individual bit. Use OS to determine whether the shift-register will output to the bus. Leave DIRA and DIRB on their default to allow information to stream in from the bus. Set LA or LB appropriately depending on where you would like to load information. Pulse the clock and reset LA/LB to load the information in the bus. Whenever Register A and B are set correctly, set the AS pin depending on whether you desire to add or subtract. Set the EO pin high to output to the bus. This will allow you to see the contents of the ALU on the bus which can be seen through the output pins. The output pins will be produced with OUT0 indicating the LSB and OUT7 indicating the MSB.

## External hardware

A sequence of 8 LEDs is hooked up to the outputs to display the final number in binary.
