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

## Projectors
* [$100 development board, BeagleBone copmatible](https://www.digikey.com/product-detail/en/texas-instruments/DLPDLCR2000EVM/296-47119-ND/7598640)
    * [Datasheet](http://www.ti.com/lit/ug/dlpu049c/dlpu049c.pdf)
    * [DMD Datasheet](http://www.ti.com/document-viewer/DLP2000/datasheet)
* [DLP7000 data sheet](http://www.ti.com/lit/ds/symlink/dlp7000.pdf) - Apparently this is the DLP unit used in the USC paper
* [TI DLPDLCR4710EVM-G2](https://www.digikey.com/product-detail/en/texas-instruments/DLPDLCR4710EVM-G2/296-46696-ND/7219324)


# References

## USC Spinning Mirror System
* [SIGGRAPH 2007 - Rendering for an Interactive 360 Degree Light Field Display](http://gl.ict.usc.edu/Research/3DDisplay/3DDisplay_USCICT_SIGGRAPH2007.pdf)
* [Multi-Use Light Engine](http://www.polarisroad.com/mule.pdf)

## Other Holography and Volumetric Imagery Items of Interest

* [Photophoretic Trap System (paywall)](https://www.nature.com/articles/nature25176)
    * [Video](https://www.youtube.com/watch?v=YRZMdQOMPNQ)
* [Voxon Photonics - Reciprocating Volumetric Display](https://www.youtube.com/watch?v=FVYoWsxqK8g)
