i01 InMoov Servo Control and Gestures in Python.
=
This is a tutorial of control your InMoov service servos in MyRobotLab(MRL) using python and creating gestures.

![001-PythonTab](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/7996ad20-a96e-4814-94a0-7767b7d93d92)


MOVING INDIVIDUAL SERVOS
= 
Movement ranges between ( 0° < 90 > 180° ). This will apply to your limited servo's Min/Max settings as well and keep within your set limits. 
- Think of 0° as max rotation according to your Min/Max limits in one direction
- 180° as max rotation in the opposite direction.
- 90° will be your center position. 

![002-Limits](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2ed4cbcb-e530-48a9-853b-fb986201dd59)



.moveTo()
=
Using the .moveTo() command line, we will be adding the desired position we want the servo to move to within the "( )".
- Example: i01_torso_midStom.moveTo(180)

![003-midStom180](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/147d798e-2960-428b-8284-aabb0e732b6c)

You can see here, it has moved the slider to the 180 position, which still have my Min/Max limits applied.
![004-midStom180b](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/80adbcf4-b787-400e-a95f-66bf9bea28f6)




.rest() 
=
Using .rest() will return "servo" to your defined rest position.

REST SLIDER PIC HERE

- Example: i01_head_neck.rest() 



MOVING MULTIPLE SERVOS AT THE SAME TIME
= 

Replace stuff from the PDF with MRL pics and examples. .. yup. 


=======================================================

THIS WHOLE PAGE WILL BE UPDATED WITH PICS, MAGIC AND MORE. 

.... But I'm going to bed first. *beep boop*
