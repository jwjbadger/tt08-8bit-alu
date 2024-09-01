<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

The project currently works by including a 16-bit shift register connected to the first input. This is conceptually broken into two 8-bit registers that may be added together. The two numbers are then brought into a very simple ALU that may adds them using logic gates (based around a 1-bit adder with a carry pin). The final carry pin is ignored and the output is displayed.

## How to test

Input your two numbers MSB first, pulsing the clock after inputting each individual bit. The output will be produced with OUT0 indicating the LSB and OUT7 indicating the MSB.

## External hardware

A sequence of 8 LEDs is hooked up to the outputs to display the final number in binary.
