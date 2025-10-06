For an overview of the parallel microscopy project, start here: https://github.com/parallelmicroscopy/overview

For software, see: https://github.com/parallelmicroscopy/RAP-software

<b> Build instructions: </b>

This is a 24 well variant of the system described here: https://elifesciences.org/articles/56426.  The main differences are its inverted (parabolic reflector on the bottom).

<i> Things to keep in mind: </i>

1) It uses 50 mm FL objective lenses, for a magnification of 2X. 

2) It uses a combination of 3D printed parts and purchased optomechanics (1/2 inch steel posts + post holders).

3) It is a 24 well imaging system (not a 96 well imaging system as described in the original publication). <i> The current design assumes the spacing of the wells is 18mm - please ensure that your 24 well plates have this exact spacing.</i>

4) Image collection and LED control is through a PC or Mac computer (desktop or laptop).

5) For the software, see : https://github.com/parallelmicroscopy/RAP-software 

<b> Construction tips: </b>

The system is build around a stack of 3D printed plates that hold the lenses, camera, and 24 well plate at user defined distances from each other and a parabolic reflector. The plates attach to 4 1/2 inch optical posts. A binder clip (https://www.staples.ca/collections/binder-clips-8639)  can be used to fix the position of any plate (they hold by friction). Most adjustments are done 'by hand' so <b>care must be taken to ensure that the following conditions are met</b>:

i) The 50 mm FL objective lenses are 50mm beneath the 24 well plate.

ii) The camera sensor is 100 mm above the parabolic reflector.

iii) The camera is positioned directly above the center of the parabolic reflector.

The lenses and camera share a housing, so focus is achieved by moving the sample holder as the camera position is set by the focal length of the parabolic reflector. The current design includes a flexure stage and 50ml syringe which can be used to adjust the height of the sample holder (attach a second syringe to the first one to adjust the height of the sample), but this is not necessary: the sample holder can be replaced by a single plate holder (part 'a') in the diagram, and the height adjusted by hand. You can use a leveling tool (e.g. https://www.thorlabs.com/thorproduct.cfm?partnumber=LVL03) to ensure the vertical plates are parallel to each other.

<img width="1496" height="348" alt="image" src="https://github.com/user-attachments/assets/762a79ff-53e7-40bb-b597-1341abf5784e" />
<br>
<b> 3D printed parts: </b>


The following pieces should be printed from PLA using a conventional 3D printer (e.g. Bambu X1 Carbon, or Prusa MK3).

a) plate holder (with baffle to reduce stray light - a second lens holder without lenses)

b) parabolic mirror holder

c) 24 element lens array (plano-convex, 50mm focal length, 12.5 mm diameter, glass)

d) Periscope (two flat mirrors, 50mm x 125 mm, 3.1mm thick (float glass))

e) Lens holder with side attachment for the camera.

f) LED array holder with collimating lenses (10 mm diameter, 15 mm focal length, clear plastic)

g) Sample holder (24 well plate, 18mm pitch, 13.5 mm diameter, plastic bottom)


<b>Camera:</b>

The camera used in the current configuration is an Allied Vision Alvium 1800 U-052m:

https://www.edmundoptics.ca/p/allied-vision-alvium-1800-u-052m-117-05mp-c-mount-usb-31-monochrome-camera/48246/

The camera is a 7.3 × 5.6 mm square CMOS sensor mounted in a <b>CS</b> housing (CS-mount   flange focal distance (FFD) = 12.526 mm, and the outer diameter of the cylindrical lens mount is 1 inch ). A camera with a <b>CS-mount</b> housing is needed for this system as a conventional 'C' mount blocks light at oblique angles. Alternatively you can remove the camera housing altogether, but if you do so add a small cooling fan to disipate heat from the camera. 

<b> Optics:</b>

Parabolic reflector: <b>1</b> x https://www.edmundoptics.ca/p/220mm-dia-x-100mm-fl-alum-coated-parabolic-reflector/23405/

50 mm FL 12.5 mm diameter plano-convex lenses: <b>24</b> x  https://www.edmundoptics.ca/p/37796/38881/

flat 50x125 mirrors: <b>2</b> x https://www.edmundoptics.ca/p/50-x-125mm-4-6lambda-mirror/2310/

Optional: In addition, illumination uniformity can be improved by using plastic collimating lenses between the LED array at the sample.: e.g. https://www.aliexpress.com/i/32545080396.html (- the lenses can be removed from their holders and placed in 3D printed part 'f' above).

<b> LED array: </b>

The array consists of 24 Dotstar LEDs (LEDs: https://www.adafruit.com/product/2343) positioned on a grid with 18mm pitch.
The LED array was custom built and assembled by PCBway (at a cost of about 35$ per array with 5 array minumum order).  <i>Gerber files are available on request</i>.

Alternatively, a commercially available LED array can be used e.g. https://www.adafruit.com/product/1430. But be aware that there are a few disadvantages. i) First, the LED spacing doesn't exactly match (there will be a slight shift noticable near the edge of the multiwell plate); ii) The commercial array also uses slower pixels with different wiring and timing requirements (Neopixels); iii) The Arduino control software would need to be altered to account for the diffent pixel number (every second pixel would be used) and pixel architecture. The software uses the FastLED.h (https://github.com/FastLED/FastLED) library so the changes would be relatively simple. Its worthwhile noting that the original publication used Neopixel array (https://elifesciences.org/articles/56426), and it was effective.


<b> LED array control: </b>

The LEDs used in the array are Dotstar 3 color LEDs. They can be controlled by a standard Arduino Uno microcontroller.

https://store-usa.arduino.cc/products/arduino-uno-rev3?srsltid=AfmBOopXxBkr__GUeiH5OznG9X-kM2l1Z6z6UYeTNxjmHn4hPxC6iHAW

<i>Please note that if you purchase an Arduino compatible microcontroller instead of the official one above, you may have to edit the software to ensure that its recognized.</i>


<b> Commercial optomechanics: </b>

In addition to the 3D printed parts, you will need <b>1/2 inch optical posts, post holders and hardware</b>:

2 x Ø12.7 mm Optical Post, L = 300 mm: https://www.thorlabs.com/thorproduct.cfm?partnumber=TR300/M

4 x Ø12.7 mm Optical Post, L = 250 mm: https://www.thorlabs.com/thorproduct.cfm?partnumber=TR250/M

4 x Ø12.7 mm Optical Post, L = 50 mm: https://www.thorlabs.com/thorproduct.cfm?partnumber=TR50/M

8 x Right-Angle Clamp for Ø1/2" Posts: https://www.thorlabs.com/thorproduct.cfm?partnumber=RA90/M

1x 150 mm x 300 mm Aluminum Breadboard: https://www.thorlabs.com/thorproduct.cfm?partnumber=MB1530/M

and M6 screws (e.g.): https://www.thorlabs.com/thorproduct.cfm?partnumber=SH6MS20


<b> Cables: </b>

Allied Vision recommends the following cables for their camera:

1) A USB 3 cable connects the camera to the PC: https://www.digikey.ca/en/products/detail/allied-vision-inc/12327/12083506
  
2) A trigger cable connects the Arduino to the camera: https://www.digikey.ca/en/products/detail/allied-vision-inc/12322/11200629

   <i>Pin 2</i> from the trigger cable should be connected to <i>Arduino pin 10</i>,  and <i>pin 6</i> from the trigger cable should be connected to <i>Arduino ground.</i>

Less expensive versions of the above cables also work in our experience.

**Finally** ... keep in mind that the hardware and software for this project are actively being worked on. Please contact [gil.bub@mcgill.ca](mailto:gil.bub@mcgill.ca) prior to starting your build for last-minute construction tips.

 
