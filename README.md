# Introduction

This is a collection of resources and developments related to the pursuit of a homebuilt holographic/volumetric display.
The aim is to reimplement the system described in a [SIGGRAPH 2007 paper](http://gl.ict.usc.edu/Research/3DDisplay/3DDisplay_USCICT_SIGGRAPH2007.pdf).

The project is in the early exploratory stage currently, and there are many challenges ahead. 

# Current Challenges

* Where to procure anisotropic diffusion film; required characteristics
* Minimum viable projector -- must be suitably bright, capable of ~4800 FPS, and as inexpensive as possible.
  * Any DMD-based projector should be able to accomplish the required frame rate
* How to balance the spinning element
* How to implement the FPGA frame rate hack (achieve higher frame rates at lower color depth)
  * Mk1 will use a microcontroller and hopefully that will be good enough.

# Component Index

Below is a list of component suppliers and data sheets -- some are provided for reference, others as candidates for inclusion in the finished system.

# Display System

### Projectors

Choosing the right projector components is crucial to the success of this project. The requirements are roughly as follows:

* 1024x768 output resolution
* Capable of 4800

#### TI DLP Lightcrafter 2000
* [$100 development board, BeagleBone copmatible](https://www.digikey.com/product-detail/en/texas-instruments/DLPDLCR2000EVM/296-47119-ND/7598640)
    * Projector system: Texas Instruments DLP Lightcrafter Display 2000 - [datasheet](http://www.ti.com/lit/ug/dlpu049c/dlpu049c.pdf)
    * Digital Micromirror Device: Texas Instruments DLP2000 - [datasheet](http://www.ti.com/document-viewer/DLP2000/datasheet)
    * Display controller: Texas Instruments DLPC2607 - [product page](http://www.ti.com/product/DLPC2607), [datasheet](http://www.ti.com/lit/ds/symlink/dlpc2607.pdf)
* [DLP7000 data sheet](http://www.ti.com/lit/ds/symlink/dlp7000.pdf) - Apparently this is the DLP unit used in the USC paper

### Bigger/Costlier

* DLP5500 DMD - $540 USD from [digikey](https://www.digikey.com/products/en?mpart=DLP5500BFYA&v=296)
* DLPC200 - $200 USD Controller supporting 5000 Hz binary image rate - [product page](http://www.ti.com/product/DLPC200), [datasheet](http://www.ti.com/general/docs/lit/getliterature.tsp?genericPartNumber=dlpc200&fileType=pdf)

#### DLPDLCR4710 - $1037 USD from digikey
* Projector system: [TI DLPDLCR4710EVM-G2](https://www.digikey.com/product-detail/en/texas-instruments/DLPDLCR4710EVM-G2/296-46696-ND/7219324)

# Rotating Platform

## Servos 
## Controllers
* [O Drive](https://odriverobotics.com/#odrive)


# References

## USC Spinning Mirror System
* [SIGGRAPH 2007 - Rendering for an Interactive 360 Degree Light Field Display](http://gl.ict.usc.edu/Research/3DDisplay/3DDisplay_USCICT_SIGGRAPH2007.pdf)
* [Multi-Use Light Engine](http://www.polarisroad.com/mule.pdf)

## Other Holography and Volumetric Imagery Items of Interest

* [Photophoretic Trap System (paywall)](https://www.nature.com/articles/nature25176)
    * [Video](https://www.youtube.com/watch?v=YRZMdQOMPNQ)
* [Voxon Photonics - Reciprocating Volumetric Display](https://www.youtube.com/watch?v=FVYoWsxqK8g)
* [Andrew Maimone](http://cs.unc.edu/~maimone/), Computer Science/3D Display researcher

## Papers We'd Like to Read

* Han and Perlin 2003 - Measuring bidirectional texture reflectance with a kaleidoscope

## BGA References

* [Working with BGA components](http://hforsten.com/making-embedded-linux-computer.html) (Designing a PCB for a 217-ball ARM processor)
* [Stackoverflow on BGA in Eagle](https://electronics.stackexchange.com/questions/349810/how-to-properly-define-bga-footprint-in-eagle)
