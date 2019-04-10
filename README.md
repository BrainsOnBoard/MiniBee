# MiniBee Design files
Design files and instructions for the Brains On Board MiniBee quad rotor platform

## Components:
- Diatone Grasshopper 160 Frame
- Airbot Asgard/Asgard32 Flight Controller (Asgard32 has a barometer if required)
- 4 x EMAX RS1106 II motors
- DYS 3020 Propellers
- Raspberry Pi Zero W
- Raspberry Pi Zero camera (50 degree)
- Macro lens (e.g. https://amzn.to/2I5PW7b)
- Bubblescope 360 panoramic lens or other hemispherical mirror
- Adafruit BNO055 Orientation Sensor or other
- MicroUSB connector
- XBee3 2.4Ghz
- Many M2 7mm hex screws
- 6x M2.5 25mm nylon bolts and nuts

## Step 1: mount the motors
There are four M2 screws needed per motor. At this point the optional landing struts that allow VICON reflective trackers to be mounted can be affixed below the motors and frame, if required.
![Alt text](MiniBee_build_1.png?raw=true "Title")

## Step 2: solder motors to Asgard
The Asgrad will be oriented upside down from default to make the build work better. This means that the STM32 should be on the TOP. Rather than adjust the Flight Controller (FC) mixer a lot we can simply wire the motors to the opposite side of the craft. Note that the middle wire of the motor ALWAYS goes to the middle pad of the FC ESC, and the two other wires, if switched, will simply reverse the motor direction. The BetaFlight Configurator can be used to test the motor direction before fixing the FC in place - note the warnings given and don't attach props while testing!
![Alt text](MiniBee_build_2.png?raw=true "Title")

## Step 3: vibration mount the Asgard
Rubber o-rings should be used between each of the layers to give good vibration damping. The nuts of the nylon bolts should be loosely tightened. After you are happy, use pliers or scissors to snip the excess nylon bolt.
![Alt text](MiniBee_build_3.png?raw=true "Title")

## Step 4: mount the Pi and solder the orientation sensor 
The orientation sensor should be wired as in the Adafruit guide [here](https://learn.adafruit.com/bno055-absolute-orientation-sensor-with-raspberry-pi-and-beaglebone-black/hardware). The Pi is mounted by slipping it under the notches at the back of the structure, then pushing it down at the front and lining the holes with those on the structure.
![Alt text](MiniBee_build_4.png?raw=true "Title")

## Step 5: mount the camera and lens
The lens should push fit into the camera structure as shown. The camera should be trapped between the camera structure and main structure. Nylon bolts and captive nutes secure the structures together at the neck, with the option of two smaller nylon screws (M2 is best) at the head either side of the lens.
![Alt text](MiniBee_build_5.png?raw=true "Title")

## Step 6: mount the mirror
The mirror can e removed from the bubblescope by snapping the stem of the scope and working the stem until it disconnects. At this point the remaining peices will slide off leaving the mirror with a mount hole through the centre. Fix the mirror onto the top of the camera structure using a nylon bolt and nut.
![Alt text](MiniBee_build_6.png?raw=true "Title")

## Step 7: connect the XBee3 module
The best way to connect the XBee3 to the Asgard is by purchasing a JST-1.0 4pin pre wired cable, and then soldering the ends onto teh MiniBee. The required connections are TX, RX, 3.3V power and GND. IMPORTANT: UART6 of the Asgard is the only one that can supply 3.3V powwer, and you must break the trace on the jumper pads that default the power to 5V and resolder for 3.3V, as per the Asgard information sheet [here](https://i.pinimg.com/originals/00/42/5b/00425ba4a4a2082930bc3ae4fa60683c.jpg). Make sure to test the volteage with a multimeter prior to connecting the XBee3 or you will destroy it!
![Alt text](MiniBee_build_6.png?raw=true "Title")

## Step 8: power the Pi
The next step simply involves connecting power to the Raspberry Pi Zero W. This can be done from the Asgard MicroUSB port using a patch cable, or by soldering a MicroUSB connector for 5V and GND to the corresponding pads on the Asgard.
