# Prototypes
## Mk 1
Threevee Mk. 1 will consist of:
* DLP2000 ($30 low-res DMD)
* DLPA1000 ($6 PMIC/LED driver)
* Microcontroller (32F769IDISCOVERY [[overview](https://www.st.com/en/evaluation-tools/32f769idiscovery.html)])
* Light source (need to research specific requirements)
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


# Test Equipment

Been kicking around ideas about how to measure the frame rate that this sombish can put out. Short of a super high FPS camera, the best idea so far is to build a small test harness with a fixed spot for the DMD to sit, with a light aimed at it such that it reflects into several photoresistors. The photoresistors have to be fast/responsive. Then we can attach the resistors to an oscilloscope or logic analyzer.

The simplest setup would be a single photoresistor, with a test program to flip the mirrors all on and off as fast as possible.
Ideally we would have 11 sensors and arrange them in such a way that we could align a segment of the projection with each of them. With 12 segments, we could encode up to 4096 different values. A 12-channel logic analyzer might not be available/feasible, but even with just a few we could devise a sequence to give some indication of how many frames into the test sequence we are.

Dunno.
