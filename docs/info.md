<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
Cordic-16 is a ROM Less cordic implementation with 16 bit Fixed point input ( 1 sign bit 3 int and 12 bit fraction).

The core uses SPI for interacing ( one byte at a time).



## How to test

The cordic is interfaced using SPI and one byte at a time we core expects 8 byte's (64 bit input) in this format {in_atan_0,in_aplha,in_x,in_y} where each of them are 16 bit each.
After Receiving these input the the engine generated the output in these format {out_alpha, out_costheta, out_sintheta} were each of them is 16 bit thu we receive 6 byte total from spi.

Here 


|  Signal name           | Details      |
|------------------------|------------  |
|     in_y               | scaled y_cordinate of input vector (0 in case of calculation of sin and cos)|
|     in_x               | scaled x_cordinate of input vector          |
|     in_aplha           | input angle in radian            |
|     in_atan_0          | intial tylor series approcimate value for better accuracy             |
|     out_sintheta       | output costhetha value             |
|     out_costheta       | output sinthetha value             |
|     out_aplha          | output conversed value of input angle (0 in case of sin and cos calculation)             |




## External hardware

Externally a Spi master is Required to communicate and send the input data to the Cordic.

We have used RP2040 (Pico) for all our testing.


### Reference 

A lot more about cordic can be understood from this paper 
 * [50 Years of CORDIC : Algorithms, Architectures, and Applications](https://ieeexplore.ieee.org/document/5089431)

