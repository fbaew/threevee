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


# Prototypes
## Mk 1
Threevee Mk. 1 will consist of:
* DLP2000 ($30 low-res DMD)
* DLPA1000 ($6 PMIC/LED driver)
* Light source (need to research specific requirements)
* FPGA development board (need to research specific requirements)
* Crude optics (need to research specific requirements)

### Micromirror Device Considerations

It's Unclear if DLP2000 can be modulated fast enough (5000fps). Suppose it can do 30 FPS @ 24 bits OOTB, that's 720 FPS @ 1 bit.
Since we are only using one output color (instead of having to cycle through RGB channels), we can triple that for 2160 FPS.
The data sheet suggests that the individual mirrors can perform numerous (at the very least, 10) landed duty cycles. 

The possibility of a sustained 50/50 duty cycle suggests that at a minimum,
can double the output frame rate to 4320 (or even 4321) FPS if we forego dynamic
range completely. I think in reality, the mirrors can go much faster. If we can 
turn a mirror on for a 10/90 duty cycle, we should be able to modulate it 10 
times per frame, so we could potentially go from 2160 FPS to 21600 FPS. 

It might prove unrealistic to turn out >20000 FPS but that's obviously 
unnecessarily high so (apart from resolution), the DLP2000 might even be up 
to the task in production.

### Power Controller Considerations

The DLP2000 describes its powerup procedure in fair detail, so it is probably possible to perform the controller's 
function on the FPGA, but the recommended driver IC is $6 so for the prototype it should be just fine.


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
