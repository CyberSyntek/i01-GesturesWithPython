i01 InMoov Servo Control and Gestures in Python.
=
This is a tutorial of how-to control your InMoov service servos in MyRobotLab(MRL) using python and creating gestures.

*This is not actually the beginning of this tutorial* Still need to write this part out.

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

Using the hashtag symbol. We can let python know it should ignore any lines beginning with "#" and the text will turn green.
- This is useful for making notes for yourself or others within your code.
- You can also use this to disable lines of code that you don't want read. Useful for temporarily disabling lines or keeping the code still written out that you may want to use at a later time.

.moveTo()
=
Using the .moveTo() command line, we will be adding the desired position we want the servo to move to within the "( )".
- Example: i01_torso_midStom.moveTo(180)

![003-midStom180](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/147d798e-2960-428b-8284-aabb0e732b6c)

You can see here, when I click back to the i01_torso_midStom servo service, it has moved the slider to the 180 position.

![004-midStomB](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3d74e6fd-1d27-4130-85ba-2d4c588bf03a)

MOVING MULTIPLE SERVOS AT THE SAME TIME WITH .moveTo()
= 
You can move as many DIFFERENT servos as you want at the same time!

![MultiServo1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2dc2f2c3-b669-4f5d-8c47-51a9baf4404e)

Moving the SAME servo more than once will be continued below in "THE IMPORTANCE OF SLEEP".


.rest() 
=
Using .rest() will return the servo to your defined rest position.
![Rest0](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/4ac194f9-026c-492a-84ff-3de7a4080993)

.rest() will function the same way as if you click the Rest button in the servo service.
![Rest](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/9d8cc71f-9509-4473-b0d0-0c7bdd4cc915)

This can make life easier for you if you don't remember all rest positions.





APPLYING SPEED LIMITS
= 
When changing the speeds of you servos, you are actually setting speed limits to further reduce the speed of a servo.
The speed limit settings range between ( 0 - 200 + None )

- 0 - Slowest (likely not moving at this speed)
- 200 - Fastest "while still limited"
- None - Removes all speed limits = FULL SPEED (MAX)


.setSpeed()
= 
Using the .setSpeed() command line, we will be adding the desired speed limit we want set for the servo within the "( )".

INSERT PIC 

.setMaxSpeed()
= 
Alternatively you can also use .setMaxSpeed() to accomplish the same speed limit removal as .setSpeed(None) , Either way will work fine.

INSERT PIC

SPEED LIMIT POSITIONING IN YOUR CODE
= 
The desired speed limit for a servo must be set prior to moving the servo for the limits to apply. / .setSpeed() line will be written above the .moveTo() line.

INSERT PIC

THE IMPORTANCE OF SLEEP
= 
sleep() will be essential for you to get used to using as it plays such a big role in creating gestures, amongst other things.

The sleep() command line is what you will add to your code to break servo movements apart and let python know that it can wait a certain amount of time and then move onto the next movement line.

You will add the desired time length within the "( )" to add a pause before python moves to the next lines. You can use either milliseconds or seconds in the "( )" to create a pause/break.

INSERT PIC / (10s / 1s / 0.5s etc)

The following examples will hopefully show you why sleep() is so important.

INSERT PIC: Example 1



You will NEED to add sleep() to your code to let it know there is a break between movements of the same servo! You will see in the following example why !!!!!

INSERT PIC: Example 2: BAD EXAMPLE (What not to do)

This will try and move the i01_head_rothead to the 130 and 90 position AT THE SAME TIME! Without adding a sleep() between the lines, python won't know it is meant as two seperate movements. *edit* 

Moving multiple servos to various positions
=
As mentioned earleir, you can move as many different servos as wanting at the same time. Now we will move 2 servos together, sleep, and move them both again, sleep and move again.

INSERT PIC:


Applying various speed limit settings to multiple servos for multiple movements.
= 

In this example, you can see how to apply speed limits + move multiple servos > sleep > remove limits + move the same servos again.

INSERT PIC:

Not enough sleep!
= 

The servo will not have enough time to reach the 180 position before it begins to move again to the 0 position.

INSERT PIC:

The sleep timer is much too short in this example. You need to give the servo a reasonable enough time to reach its position before sending it to the next position.

Tips for a good sleep!
= 

It will take some practice getting used to how long sleep timers will need for each servo to be able to reach from position to position.
- Experiment with different timers for different ranges!
- I suggest starting with slightly longer sleep times, run the code, reduce/adjust as needed, repeat until you are happy with it.

=======================================================

SERVO GROUPS EXPLAINED
= 

Looking at the example, we will see four numbers within the ( ). The order in which they appear is important!

INSERT PIC: 01.moveArm("left",10,20,30,40)








=======================================================

*beep boop* Updates in progress!
