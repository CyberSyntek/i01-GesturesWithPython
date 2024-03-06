i01 InMoov Servo Control and Gestures in Python.
=
This is a tutorial of how-to control your InMoov service servos in MyRobotLab(MRL) using python and creating gestures.

![i01main1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/cb65f2df-41f2-4ede-9c3f-9c487263f5ea)




![PythonNewFile1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/6b2e63fe-8790-4ee3-a0ba-3b0c987bfece)


![001-PythonTab1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/e5ff36b9-5454-43ea-af59-c05b9519ac00)





MOVING INDIVIDUAL SERVOS
= 
Movement ranges between ( 0° < 90 > 180° ). This will apply to servos with limited Min/Max settings as well and keep within your set limits. 

In the image below, you can see that I have my "i01_torso_midStom" servo limited to Min:60 / Max: 120.
![002limits1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f23ce389-6268-4ff4-ae24-aa372cc0561c)


When moving the slider to the 0 position, it is moving the servo to my defined Min: 60 position despite still using a 0-180 range slider.
![MidStomSlider1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/c5ee905f-87d2-474e-bb82-f95e19446e57)

- Think of 0° as max rotation in one direction (according to your Min/Max limits)
- 180° as max rotation in the opposite direction. (according to your Min/Max limits)
- 90° will be your center position. (according to your Min/Max limits)

These same ranges will apply when moving your servos in python.

"#" In python
= 
If you are completely new to python, it is a good idea to remember the # symbol. 
![Hashtag](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/c03c05d0-f4a8-45d8-903e-59449f2ad4d2)

Using the hashtag symbol. We can let python know it should ignore any lines with "#" in it and the text will turn green.
- This is useful for making notes for yourself or others within your code.
- You can also use this to disable lines of code that you don't want read. Useful for temporarily disabling lines or keeping the code still written out that you may want to use at a later time.

.moveTo()
=
Using the .moveTo() command line, we will be adding the desired position we want the servo to move to within the "( )".
- Example: i01_torso_midStom.moveTo(180)

![003-midStom180](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/147d798e-2960-428b-8284-aabb0e732b6c)

You can see here, when I click back to the i01_torso_midStom servo service, it has moved the slider to the 180 position.
![004-midStomB](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3d74e6fd-1d27-4130-85ba-2d4c588bf03a)



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
