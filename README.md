i01 InMoov Servo Control and Gestures in Python.
=
Welcome to the how-to control your InMoov servo services in MyRobotLab(MRL) using python and creating gestures tutorial.

#INSERT IMAGE

This tutorial assumes that you have already have a basic understanding of using MRL and the InMoov services (i01).  
- Know how to launch servo services from the InMoov (i01) UI, calibrate and move your servos with the sliders in the servo services.


WHEN IN DOUBT, UPDATE!
= 

![MRLheader](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/8bece874-cb88-4e35-8e60-c36b92f1eaff)

MyRobotLab (MRL)'s latest edition (Nixie) is still receiving constant updates, bug fixes, etc etc. 
- Everytime something new is added, a bug is fixed, etc etc, an updated Ver of MRL releases.
- If you notice anything in this tutorial not working, it likely means you are using an outdated copy.
- Try and not fall too many versions behind. 

Download latest version here:

https://build.myrobotlab.org:8443/job/myrobotlab/job/develop/lastSuccessfulBuild/artifact/target/myrobotlab.zip

You can transfer your saved services (calibrated servos, etc, etc) easily over to the updated version. 
- Data for anything you have saved will be in the date folder. Example: "myrobotlab-1.1.1402\data\config". 
- Tranfer that folder over to newest version's data folder. "Example: "myrobotlab-1.1.1411\data\config".
 - Back in business. :)






INMOOV SERVO SERVICES
= 
As you open up the default InMoov Servo services, you will see them displayed on the left side panel. 
- They are displayed with a Servo Icon, followed by the service names for each part.

![ServoServices0](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/8efaaadc-8526-4296-a853-af70d069bc26)

The names of these servo services is what will be especially important as we move onto python. 



INTRO TO PYTHON
=
You can access python from the tab on the left side. It will be in your service listing by default. 
![i01main1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/cb65f2df-41f2-4ede-9c3f-9c487263f5ea)

Since we will be experimenting and you may have other tabs open which launch with your i01 services by default, click "New" and enter a name. 
- "Test" for example.

![PythonNewFile1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/6b2e63fe-8790-4ee3-a0ba-3b0c987bfece)

Now you should have a new tab open for whatever you named the file. "Test".

![001-PythonTab1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/e5ff36b9-5454-43ea-af59-c05b9519ac00)






"#" In python
= 
If you are completely new to python, it is a good idea to remember the # symbol. 

![Hashtag](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/c03c05d0-f4a8-45d8-903e-59449f2ad4d2)

```py
#THIS IS AN EXAMPLE OF USING THE HASHTAG "#". 
```
Using the hashtag symbol, we can let python know it should ignore anything following a "#" symbol. Any text following # will be displayed in green.
- Python will ignore all green text.
- This is useful for making notes for yourself or for others within your code.
- You can also use this to disable lines of code that you don't want read. 
- Useful for temporarily disabling lines OR maintaining code you don't want read for potentially using again in the future. (Not so temporarily).

LINE SPACING IN PYTHON
=
Line spacing (How many blank lines between lines) will not matter in python. 
- You can spread lines out as much as you want to make things easier to find/manage.

![Linespacing](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/eca0ba88-62de-448d-9abd-2951c4e62ff5)

```py
#THIS IS AN EXAMPLE OF USING LINE SPACING.



#YEP! 
```


Execute / Run a script
=

To run a script you have written out, hit the "execute button".
![Execute1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/243661ae-afe6-4eee-9523-c6df9cd53b36)

You can run the following example from the above image for yourself to test it. It will do NOTHING! :D

```py
#THIS IS A TEST SCRIPT WITH NO FUNCTION, EXECUTE ME!
```

ADJUSTING SERVO SERVICE NAMES FOR PYTHON
= 

Python is very picky with names. It generally does not like the names of the i01 services as they contain too many dots. 

![ChangeNames0](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/70bf1d0f-a946-44ac-8194-2e8cdd889e18)

Make sure when using python to change the names of your servo services to use underscores " _ " instead of dots " . "
- i01.head.neck >>> i01_head_neck
- i01.leftArm.bicep >>> i01_leftArm_bicep
- etc, etc. 

Here is a list of all the current i01 InMoov servo services currently available at the time of writing this tutorial.

![Servos1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/9cd9e0e9-cfdb-4492-ada6-77b725090cd4)

CAPITALIZATION / CASE MATCHING MATTERS!
= 
If you're using for example i01_head_neck , it CANNOT be written with a different case of letters. 

![CasematchingMatters](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/1c0d2496-72e8-4c0b-9c95-d421d704ebdf)

- It must be written with the same matching character case for python to know it is the same service.



ERROR
=
If you forget to change the service names accordingly, you will likely see a traceback error like this.

![traceback](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/213a07e9-c496-48e5-9b55-8b18c9e0479a)

Alternatively, if you do see errors at any time, the error will help you identify why there is an error and which line it can be found in.
- You will see the error listed in the bottom "console". 

![Console1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/95cfa139-faff-46da-930c-64693e4c1de6)

Here is another example of an error and how to identify it within the console. 
![TraceErrorHelp](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/930cf690-ac0f-4854-89a7-19c2f61dfebc)

In this case, the traceback error told us...
- The error occured in line 1. 
- i01_head_neck is not defined. This is because it does NOT currently exist. I have not started the i01.head.neck servo service yet.


SERVO MOVEMENT RECAP (Sliders VS Python)
= 
Movement ranges between ( 0° < 90 > 180° ). This will apply to servos with limited Min/Max settings as well and keep within your set limits. 

In the image below, you can see that I have my "i01.torso.midStom" servo limited to Min:60 / Max: 120.

![002limits1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f23ce389-6268-4ff4-ae24-aa372cc0561c)


When moving the slider to the 0 position, it is moving the servo to my defined Min: 60 position despite still using a 0-180 range slider.

![MidStomSlider1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/c5ee905f-87d2-474e-bb82-f95e19446e57)

- Think of 0° as max rotation in one direction (according to your Min/Max limits)
- 180° as max rotation in the opposite direction. (according to your Min/Max limits)
- 90° will be your center position. (according to your Min/Max limits)

These same ranges will apply when moving your servos in python as well. Your servos will act the same way as the sliders.


.moveTo()
=
Using the .moveTo() command line, we will be adding the desired position we want the servo to move to within the "( )".
- Example: i01_torso_midStom.moveTo(180)

![003-midStom180](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/147d798e-2960-428b-8284-aabb0e732b6c)

```py
i01_torso_midStom.moveTo(180)
```

You can see here, when I click back to the i01.torso.midStom servo service, it has moved the slider to the 180 position.

![004-midStomB](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3d74e6fd-1d27-4130-85ba-2d4c588bf03a)

MOVING MULTIPLE SERVOS AT THE SAME TIME WITH .moveTo()
= 
You can move as many DIFFERENT servos as you want at the same time!

![MultiServo1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2dc2f2c3-b669-4f5d-8c47-51a9baf4404e)

```py
i01_torso_topStom.moveTo(90)
i01_torso_midStom.moveTo(90)
```

Moving the SAME servo more than once will be continued below in "THE IMPORTANCE OF SLEEP".


.rest() 
=
Using .rest() will return the servo to your defined rest position.
![Rest0](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/4ac194f9-026c-492a-84ff-3de7a4080993)

```py
i01_torso_midStom.rest()
```

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

SIDE NOTE: The speed limits only range between 0-200 with the slider. It is possible to go beyond 200 with python.
- It is hard to tell you exactly what the max limit range will be as it will depend on your servos. 
- If you set it too high, you may not even notice a difference between the servos max speed and the limits applied.
- You likely won't need to go beyond 200, just it maybe possible. (You can experiment if so desiring to do so.)


.setSpeed()
= 
Using the .setSpeed() command line, we will be adding the desired speed limit we want set for the servo within the "( )".

![NeckSpeed](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/1450af15-95eb-44dc-80f4-f7c4bc67002f)

```py
i01_head_neck.setSpeed(100)
```

As you can see, the speed limit was also changed in the i01.head.neck servo service as well. 

![NeckSpeed2-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/b8ba74f0-3521-4e62-887d-1b4fb14d827d)

Side Note: I'm not entirely sure at this time if the slider is bugged or this is intentional. 
- The speed limit is set to 100, but the slider is still at the prior speed limit position. (semi useful for remembering prior set speed regardless) 
- The speed limit IS being applied correctly.

.setSpeed(None)
= 
.setSpeed(None) will remove all speed limits from the servo. 

![SpeedNone](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/85ba2e06-ec17-4197-9a15-6a16ec49a807)

```py
i01_head_neck.setSpeed(None)
```

Again if going back to the servo service, you can see that it has changed the speed limit to Max / removed limits.

![SpeedNone2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/fedb3ab6-d255-445f-9b24-141c0eb37875)


.setMaxSpeed()
= 
Alternatively you can also use .setMaxSpeed() to accomplish the same speed limit removal as .setSpeed(None). 
- Either way will work fine, they are essentially the same thing.

![SpeedMax](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/c1378723-4cc0-4b09-8ceb-4c975c7d20e6)

```py
i01_head_neck.setMaxSpeed()
```

SPEED LIMIT POSITIONING IN YOUR CODE
= 
The desired speed limit for a servo must be set prior to moving the servo for the limits to apply. 
- .setSpeed() will be written above the .moveTo() command.

![LimitPositioning](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/7efe5129-b9be-4023-a2bf-32859db1357a)

```py
i01_head_neck.setSpeed(200)
i01_head_neck.moveTo(90)
```


THE IMPORTANCE OF SLEEP
= 
sleep() will be essential for you to get used to using as it plays such a big role in creating gestures, amongst other things.

The sleep() command line is what you will add to your code to break servo movements apart and let python know that it can wait a certain amount of time and then move onto the next movement line.

You will add the desired time length within the "( )" to add a pause before python moves to the next lines. 
- You can use either milliseconds or seconds in the "( )" to create a pause/break.

![Sleeptimers](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3b8231f7-5456-4b7e-b04b-6a9ffede0375)

```py
sleep(1)
```

The following examples will hopefully show you why sleep() is so important.

You will NEED to add sleep() to your code to let it know there is a break between movements of the same servo! You will see in the following example why !!!!!

- Example 1: Move to 180 > wait 3s > move to 0 > wait 2s > return servo to center.
- The sleep timers are what allows to servo to reach its position before moving to the next.
 
![Sleepexample1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2507a03b-3551-4213-8e8c-ff821fa32119)

```py
i01_head_neck.moveTo(180)
sleep(3)
i01_head_neck.moveTo(0)
sleep(2)
i01_head_neck.moveTo(90)
```

THE BAD EXAMPLE (What NOT to do)
=
WARNING!!!! Do not attempt this example. 
- In this example, the servo will attempt to reach the 180 position and the 0 position at THE SAME TIME.
- Without adding a sleep() between the lines, python won't know that they are meant as two seperate movements.

![BadExample](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/a17d40ad-88f2-4617-bfa3-30fa86bfb69c)

Side Note: You likely won't break your servos if you forgot to include it.... but it is a good idea to try and avoid it.
- Things may get funny if you forget sleep().

Moving multiple servos to various positions
=
As mentioned earlier, you can move as many different servos as wanting at the same time. Now we will move 5 servos together.
- All servos to 180 > sleep for 5s > all servos to 0 > sleep for 5s > all servos to 90 > sleep for 0.1s.

![MultiServoMadness](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/cca4ad29-8d52-4245-91c0-8adaeda63483)


```py
i01_head_neck.moveTo(180)
i01_head_rothead.moveTo(180)
i01_head_rollNeck.moveTo(180)
i01_leftArm_bicep.moveTo(180)
i01_rightArm_bicep.moveTo(180)
sleep(5)

i01_head_neck.moveTo(0)
i01_head_rothead.moveTo(0)
i01_head_rollNeck.moveTo(0)
i01_leftArm_bicep.moveTo(0)
i01_rightArm_bicep.moveTo(0)
sleep(5)

i01_head_neck.moveTo(90)
i01_head_rothead.moveTo(90)
i01_head_rollNeck.moveTo(90)
i01_leftArm_bicep.moveTo(90)
i01_rightArm_bicep.moveTo(90)
sleep(0.1)
```

Applying various limits and positions to multiple servos in different stages.
= 

In this example, you can see how to apply speed limits + move multiple servos > sleep > repeat to your hearts content or until you go crazy. :D

![MultiStages](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/30aba3b4-61b3-47d6-bb1d-b7bad69675a9)


```py
i01_head_neck.setSpeed(150)
i01_head_rothead.setSpeed(200)
i01_head_rollNeck.setSpeed(50)
i01_head_neck.moveTo(180)
i01_head_rothead.moveTo(180)
i01_head_rollNeck.moveTo(180)
sleep(7)

i01_head_neck.setSpeed(100)
i01_head_rothead.setSpeed(None)
i01_head_rollneck.setMaxSpeed()
i01_head_neck.moveTo(0)
i01_head_rothead.moveTo(0)
i01_head_rollNeck.moveTo(0)
sleep(3)

i01_head_neck.setSpeed(200)
i01_head_rothead.setSpeed(200)
i01_head_rollNeck.setSpeed(200)
i01_head_neck.moveTo(90)
i01_head_rothead.moveTo(90)
i01_head_rollNeck.moveTo(90)
```

WARNING: Not all movements are 100% safe!
= 
It will be important when you first start playing with gestures to take it slow!

Even with a well calibrated robot, accidents can happen. Your servo calibration protects that servo and that part from breaking itself.
- It does NOT protect other servos from breaking that part.

Examples of try to avoid movements
- Index and Thumb: When closing at the same time and speed, it is possible for them to bump.
   - It is best to either adjust the speed limits or sleep timers so they will avoid each other.
  
- If the shoulders rotate servo is rotated inwards, bicep raised and shoulder moved back, the arm can hit the stomach.
  - This one can be avoided if the omoplate is also raised.
  - However: Omoplate must have power to the servo or gravity cause it to come crashing down. (Auto-Disable timers: See below)

- Certain movements with the arms are able to hit the head of the robot. 

Get comfortable with smaller ranges of movement while moving various servos before pushing them to their limits!


Not enough sleep!
= 
You need to give a servo a reasonable enough time length to reach its position before sending it to the next position.

- In this example, the .sleep() timer is set so short, the servo cannot reach the 180 posistion before moving to the 0 position.

![NotEnoughSleep](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/bb6df91f-da56-41b3-8a05-086395ed8655)

- It will still ATTEMPT to reach 180, but it's movement will get cut off and proceed to the 0 position. 

Tips for a good sleep!
= 

It will take some practice getting used to how long sleep timers will need for each servo to be able to reach from position to position.

![NotEnoughSleep2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/89cfbd62-ac0c-4023-b8e9-38e5789dd2b3)

```py
i01_torso_midStom.setSpeed(None)
i01_torso_midStom.moveTo(0)
sleep(10)

i01_torso_midStom.moveTo(180)
sleep(5)

i01_torso_midStom.moveTo(90)
sleep(2.5)

i01_torso_midStom.moveTo(0)
```

- Experiment with different length timers. 
- You will need a longer timer moving a servo from 0 to 180 than you would moving it from 0 to 90. 
- I suggest starting with slightly longer sleep times, run the code, reduce/adjust as needed, repeat until you are happy with it.

AUTO DISABLE TIMERS
= 
You will need to make sure your servos auto disable timers are long enough that the servo is able to reach its longest destination range. 
- 0-180 for example. If you servo can reach from 0 - 180 within 5 seconds for example you know it is safe.
- You can continue to reduce and repeat until you have found an ideal auto disable timer. 
- This can be a bit tricky once you apply different speed limits, so you will need to experiment.

![AutoDisableTimer](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/504ffb01-b31d-4c8c-9871-8c9a430eae28)

WARNING! - ADVANCED GESTURE AUTO DISABLE COMMANDS
= 
USE WITH CAUTION!!!!

![ServosAtRisk](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/1435675f-b96c-468e-bf9a-d00b4c320126)

You really should not use these until you are very comfortable playing around with your servos. 
- Auto disable timers are important as they help prevent your servos from burning out. 

With the following example, we can disable the autoDisable timer within python and also re-enable it.

![DangerZone](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/28efe23e-507c-4055-afc3-e65662df6e07)

USE CASE: 
- Can be useful for when we need a servo to maintain power for longer than normal to hold a position.
  - Omoplate is an example of a servo that requires power to be held up. Once autodisable kicks in, it can come crashing down.
 
- Can use useful for when using slower speed limits to avoid autoDisable timer kicking in before destination reached. 

I strongly suggest you don't use this until you have played with ALOT of gesture creation and start getting more and more fancy with them. 

```py
i01_head_neck.setAutoDisable(False)
sleep(5)

i01_head_neck.setAutoDisable(True) #REMEMBER ME!
```

And that is all I am going to cover for individual line servo commands! HOWEVER, there are more options available still! 

I'll be updating this page over the next few days, more updates to come shortly. o/

=======================================================

SERVO GROUPS EXPLAINED
= 

Servo groups are another way you can control your servos in python. 

![groupequal](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f2ed9105-c5ed-4d4b-9056-c49747b9e271)

Think of Servo Groups as a condensed version of ".moveTo()" or ".setSpeed()" for multiple servos which are sorted into limb sections. 
- head = neck, rothead, eyeX, eyeY, jaw, rollNeck
- Arm =  bicep, rotate, shoulder, omoplate
- Hand = thumb, index, majeure, ringFinger, pinky, wrist
- torso = topStom, midStom & lowStom.

Benefits of groups: 
- Hugely decrease the amount of lines in your code.

Negatives of groups: 
- You MUST remember which value represents which servo or you might move the wrong servo unexpectedly.
  - Accidents can happen when moving the wrong servos depending on the various servo positions.
- Not all servos have groups! See below in "MISSING GROUPS".

Looking at the example, we will see four numbers within the ( ). The order in which they appear is important! 

- Each of these numbers represent a specific servo and the position we want to move it to.
- In this case, the first value "10" represents i01.leftArm.bicep and that we want to move it to the 10 position.
- For ARMS and HANDS you will see either "left" or "right" initially within the ( ) which determines which side Arm or Hand you are moving.


```py
#Example: Moving all 4 "left" Arm servos (bicep / rotate / shoulder / omoplate) 
i01.moveArm("left",10,80,40,20)

#PLEASE USE EXAMPLE BELOW INSTEAD OF TESTING THIS EXAMPLE!
```

I suggest testing each servo group with only moving one servo at a time while you get used to using groups to avoid accidents. 

```py
#Example: Moving only the left bicep servo. (bicep / rotate / shoulder / omoplate) 
i01.moveArm("left",10,None,None,None)
```

More safe to try examples below!

SERVO GROUPS AND EXAMPLES
=

![Groups](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/0d79b58f-8574-407e-b8ae-cb0fcc5c15e4)

HEAD EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setHeadSpeed(200,200,200,200,200,200) #(neck,rothead,eyeX,eyeY,jaw,rollNeck)

#Moving only the neck within the group.
i01.moveHead(100,None,None,None,None,None) #(neck,rothead,eyeX,eyeY,jaw,rollNeck)
```

LEFT ARM EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setArmSpeed("left",200,200,200,200) #("left",bicep,rotate,shoulder,omoplate)

#Moving only "left" bicep within the group.
i01.moveArm("left",10,None,None,None) #("left",bicep,rotate,shoulder,omoplate)
```

RIGHT ARM EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setArmSpeed("right",200,200,200,200) #("right",bicep,rotate,shoulder,omoplate)

#Moving only "right" bicep within the group.
i01.moveArm("right",10,None,None,None) #("right",bicep,rotate,shoulder,omoplate)
```

LEFT HAND EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setHandSpeed("left",200,200,200,200,200,200) #("left",thumb,index,majeure,ringFinger,wrist)

#Moving only "left" wrist within the group.
i01.moveHand("left",None,None,None,None,None,180) #("left",thumb,index,majeure,ringFinger,wrist)
```

RIGHT HAND EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setHandSpeed("right",200,200,200,200,200,200) #("right",thumb,index,majeure,ringFinger,wrist)

#Moving only "right" wrist within the group.
i01.moveHand("right",0,None,None,None,None,None) #("right",thumb,index,majeure,ringFinger,wrist)
```

TORSO EXAMPLES:
```py
#Setting the whole group speed limit to 200.
i01.setTorsoSpeed(200,200,200) #(topStom,midStom,lowStom)

#Moving only "midStom" within the group.
i01.moveTorso(None,90,None) #(topStom,midStom,lowStom)
```

None VS None
=
![noneVSnone](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/d558a4fe-cfe7-444e-94f5-6e403ef5de3f)


Remember not to confuse "None" between movement and speed settings in groups. They have different functions.
- MOVEMENT: Ignore Servo

- SPEED: Remove limits

MISSING GROUPS
= 

V2 Head Servos
- As of when I am writing this, there are currently no group setting for the V2 head.
  - The V2 head is still very new and I believe code side things are still being planned out.

i01.head.eyelidLeft & i01.head.eyelidRight
- While there is a service for i01.head.eyelidLeft & i01.head.eyelidRight, they were not part of the official build.
  - They were added to allow people to explore with mods and are NOT part of any groups.  


SUB SERVO GROUPS
= 

There are a few V1 head servo sub-groups which were made over the years. You can use them as well if so desiring to do so.

If you ever explore the built-in gestures folder, you may come across some examples of lines looking like the following example.
- (There is more info relating to built-in gestures at the bottom of this page.)

![SubGroups](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/000d739a-7b5f-467b-9dbe-87131091fe8b)


You can see in the below example which values represent which servo. 
- They are very similar to the Servo Groups mentioned above.
  
  - Exceptions being"i01.moveHead(100,100,100,100)" as this doesn't exist at all and will cause a traceback error.
![TracebackArg4](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/683264aa-84c2-4f7e-afa2-0bc7732b736f)
  - and "i01.moveHead(100,100,100)" as the 3rd value is "rollNeck". This is the only exception in which the 3rd value servo changes. 

```py
i01.moveHead(100,100) #(neck,rothead)
i01.moveHead(100,100,100) #(neck,rothead,rollNeck)
#i01.moveHead(100,100,100,100) DOESN'T EXIST / WILL CAUSE TRACEBACK ERROR
i01.moveHead(100,100,100,100,100) #(neck,rothead,eyeX,eyeY,jaw)
i01.moveHead(100,100,100,100,100,100) #(neck,rothead,eyeX,eyeY,jaw,rollNeck) Full group. 
```

I don't personally ever use these, but they exist as an option. 
- Atleast you will understand what role "i01.moveHead(100,100)" plays now if you see it in the gestures folder.
- I believe "01.setHeadSpeed(100,100)" for example will also work for these sub groups. 


SPEECH WITHIN GESTURES
= 
In order to use speech in python, you will need a mouth.

![NeedMouth1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/84952259-3ea3-4b56-a92c-356ec4249f0f)

 ......"01.mouth" service that is. :)

![SpeakvsSpeakBlocking](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/388bcb8a-46da-4973-a95b-6b0aacc1093d)

There are two different ways to achieve speech. 
- i01.speak()
- i01.speakBlocking()

```py
#i01.speak() vs i01.speakBlocking()
i01.speak("I am speaking RIGHT NOW!")
sleep(4)
i01.speakBlocking("Now I am speak Blocking! Haha")
```

i01.speak()
=

When using i01.speak() , you will place the text you want spoken between quotes within the ( ). 
- Example:  "I am speaking"   >>>   i01.speak("I am speaking")

This is the simplest way to achieve speech.
```py
i01.speak("I am speaking now. Test test Test!")
```

Here is another example of using the same example above while the head is in motion.
```py
#You will see the head continue to move back and forth as speech is happening.

i01_head_rothead.setSpeed(50)
i01_head_rothead.moveTo(50)
sleep(1.5)

i01.speak("I am speaking now. Test test Test!")
i01_head_rothead.moveTo(130)
sleep(1.5)

i01_head_rothead.moveTo(50)
sleep(1.5)

i01_head_rothead.moveTo(130)
sleep(1.5)

i01_head_rothead.moveTo(90)
```

i01.speakBlocking()
=
Another way to achieve speaking is with i01.speakBlocking(). 

The same rule applies when using i01.speakBlocking(). Place spoken text between quotes within between the ( ). 

```py 
i01.speakBlocking("Now I am speak Blocking! Haha")
```

The major difference with i01.speakBlocking() is that it will "Block" all of the following lines in your script until it is done saying whatever is within the (). 
- This means if you have a .moveTo() command following i01.speakBlocking(), it will not move until the speech is complete.
```py 
#In this example you can see rothead will only move to the 130 position AFTER i01_mouth.speakBlocking() is complete.
i01_mouth.speakBlocking("Now I am speak Blocking! Haha")
i01_head_rothead.moveTo(130)
```

You will notice in the above example that there is no sleep() timer before the .moveTo(). 

i01.speakBlocking() is acting like a sleep timer in this situation by "blocking" all lines following until speech is complete.
- This acts as a "break" in the code which resembles a sleep() timer with the duration the length of the spoken text. 
- Because of this, sleep() is not needed. Adding a sleep() would further extend the time before moveTo() begins.

Which should I use? speak() OR speakBlocking()? 
= 
It is personal preference honestly. Extra options are always nice. 

I know Gael has used i01.speakBlocking() in various gestures over the years. 
- You can find some examples of his usage in various built-in gestures. (Info at bottom) 

Benefits of i01.speak():
- You can move various servos even while speech is occuring which is useful for more advanced gestures.
- Your bot won't come to a stand still while waiting for the spoken text to finish.
   - This means though you need to figure out sleep() timer lengths for when speech applies during which movements, etc. 

Benefits of i01.speakBlocking():
- You don't have to worry about adding a sleep() timer and figuring out time lengths. 
- You know exactly when the following lines will start since it waits/blocks until speech is finished.
- This option can make creating gestures easier/faster for you.
    - but also limits what can be done during speech. 

Generally I want various servos to be able to move even while the bot is still speaking to avoid any awkward pauses in a gesture. 
- That is why I almost always use i01.speak().
- There maybe some ideal use cases for i01.speakBlocking() which I can't think due to not using it often. *shrug*



=======================================================

DEFINING YOUR GESTURES (FORMAT AND SAVING)
=
When defining your gestures, you will need to change the format from what we have used so far. 

- The number of initial spaces doesn't matter, but must remaining consistent for all lines. 
- There are exceptions to this in more complex examples which we are not worried about at this point.

![Defining01](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/838c0355-c3a1-40e6-84a9-eb5e0753b546)

```py
def examplescripttest1():
    i01_head_rothead.moveTo(130)
    sleep(4)
    i01_head_rothead.moveTo(50)
    sleep(4)
    i01_head_rothead.moveTo(90)
#### <--- 4 spaces.

def examplescripttest2():
  i01_head_rothead.moveTo(130)
  sleep(4)
  i01_head_rothead.moveTo(50)
  sleep(4)
  i01_head_rothead.moveTo(90)
## <--- 2 spaces.

def examplescripttest3():
    i01_head_rothead.moveTo(130)
    sleep(4)
    i01_head_rothead.moveTo(50)
    sleep(4)
    i01_head_rothead.moveTo(90)
#### <--- 4 spaces with tabs. = Bad practice, but MRL saves us... this time. 
```

NOTE: You may have noticed that I have 3 different things defined here.
- You can have as many different things defined in one script as you want!
- Obviously it can be hard to find them all again easily if you add hundreds of them into the same file, but ... its possible. 

Once your script looks ready, you will need to hit execute for it to be able to run them. 
- Note: This will not "run" the individual scripts, but rather make them able to be ran as seen in the next step.

![Defining02-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/270f0b04-544b-440d-bbfd-edc9e10d6da9)

Here I have opened up another tab to be able to test the scripts from above. 
- You can see the format for how we will test them once they have been executed. (As seen above)
- In this example, I have hastagged out the other two examples so I can test one at a time. (Adding and removing #)
- Hit execute to run the script. (This time, it will move the servos or whatever is in the defined script.) 

![Defining03-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/9b4ca483-721d-4ff6-8f57-dcdcbbf204f4)

```py
examplescripttest1()
#examplescripttest2()
#examplescripttest3()
```

Here I have opened another new tab and have given it the name "exampletestscripts". 
- When hitting the save button, this is the name that it will output the .py file as. 

![Defining04-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/5bf92937-faf7-44b0-a1c0-37b82ed14779)

When the file is saved, it can be found in your MRL(ver) root folder.

![Defining05-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/19b09e18-9071-402a-8d9b-ae990104b902)

- You can change the name to whatever you want after you save it too of course. 

WARNING: RISK OF GESTURE LOSS!
=
![Warning](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/e58f0e57-ab5a-4558-af0e-3bcd14b5d3a9)


WARNING: SAVING FILES
=
If you save a file with the same name as a file still in your root directory, it will be overwritten!
- Using different names is always a good idea for safety. This is why I suggest naming your tab to whatever you want to call the file.
- Also not keeping the files in your root directory is a good idea as well which we will get into next!

WHY YOU SHOULDN'T WRITE YOUR SCRIPTS IN MRL
= 
REASONS:
- When you close MRL, whatever you have written in the python service will vanish. If you haven't saved it, it is lost.

OTHER SOFTWARE:
- I will be using VScode in these examples as it is free to download and useful for us in this situation. 
- You can download VScode here:  https://code.visualstudio.com/ 

REASONS:
- When closing VScode, your code will remain! You would need to close the specific tab for that code to get rid of it.
- This is very important for not losing your hard work on your gestures. Accidents happen or you forget to save things.

   - You can do the same type of thing using Notepad++ as well, but VScode will be used for this example.
 
![VScode3-1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/aa3db55a-7a2f-4287-ab8f-16dbf1a5ff5d)

When you first open up VScode and hit "File > New", it will appear like this. 
- Click "Select a language" and select "Python".

![VScode1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/503f9207-b1dd-4f0a-8b9a-625308679ce2)

It will now format it to look like this for you and you are good to go. Safe gesture storage = win! 

![VScode2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/48f8187a-ef39-4df7-b9d9-28261ac1862e)

Note: VScode also auto-converts tabs for you. :9 

CREATING A CUSTOM FOLDER FOR YOUR MRL CONTENT
= 

Example: Here you can see I have a MRL folder created for the various versions of MRL for when updating. 

- I have created a "Custom" folder within that folder to put my various files in when I use MRL regardless of version.
  - It can be named anything you want, the pathway to the folder files are what we are concerned with.

- The important thing is that this folder is not within any specific version of MRL.
  - With its own location, it can be applied to other versions easily.
  - Avoid using complex names or symbols is suggested as things could get strange/errors. 

For now I have moved the "examplescripttests.py" file from earlier into the root of my Custom folder.

![ExampleCustom](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/901e432d-ffab-4abb-89b8-be2bd88cf57e)

Note: "BasicMovement" I made for small basic "gestures" moving both eyes left for example. 
   - The "Gestures" folder is where I generally put things that are more complex than one or two movements. 
   - Completely upto you how you set things up and or what you keep in the folder. :) 





IMPORTING YOUR GESTURES
=

All the data from any config you have saved will be located in the Data\Config folder. 
- Start up whatever i01 services you want > runtime > save config > "whichever name."
- When loading the config name you saved it with should be listed as well. 

For example: I have named my config i01Syntek as I am running my bot "Syntek" with the i01 InMoov services. 
- This is why you can see a i01Syntek folder. :)

![Data1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/0254100b-92d5-4444-a5c2-6879b2994795)

Inside your service folder, you will want to locate the "python.yml" file and open it up. 
- notepad /note++/whatever text editor you want.
  
![Data2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/a5ed4bb6-7d0f-4a31-a48f-6dc4a1fe44f1)


You will be looking at startScripts:  
- There should be brackets [ ] by default.

![Data3](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/a4ba69c9-c794-44ed-beb1-bce5ea09cbe0)


Starting on the line following "startScripts:" you will want to list all your python scripts you want included and loaded at startup.
- inclue a - followed by the file location. Example below.

```py
- C:\MRL\Custom\examplescripttests.py
- C:\MRL\Custom\randomnametestscript.py
```
One you have entered whichever scripts you want included, save the file and then boot MRL. 

![Data4](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/da3f8f68-f2a0-46ae-a7bd-5d68f0aa5651)


Boot your config (runtime > start "saved config name") and click over to python. 
- You will see that the scripts do not autoload instantly and appear not to be there. 
- Click "load and apply configuration"

![Data5](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/9b42473f-6b8b-48d5-9c63-03fdcd6d9b97)


Now you can see the scripts are all loaded in. You do NOT need to execute them, they are loaded in as such. 

![Data6](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/4c75c509-f4da-4ffc-a5cd-2bf31f14afb5)


Now you can see I opened up a new "test" tab to try and run one of the example scripts, hit execute and magic. It works. 

![Data7](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f361a3ca-17ed-4fc4-9ed7-4e1f2584cf39)


Avoiding Missing Scripts
=
If you DON'T load your scripts into MRL after you boot up your config, and then you happen to save your config from runtime:
- They WILL vanish from the python.yml startScripts: list! 
  - Without them loading in, the config will assume startScripts is empty and overwrite that file. 
  - You will need to enter them into the list again if that happens.
    
![Data8](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/4a42236d-ae1e-4b88-b1ea-fd01f1edb8e8)


It can be useful to make a text backup of the python.yml file to be able to copy and paste back in the script list - just incase. 
 - This can save you needing to remember which scripts you have included, if for example you have a long list of scripts.

![Data9](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3dfc7063-51f7-4e7f-abb3-54779aeb3d66)



CREATING A CUSTOM CHATBOT FOR VOICE COMMANDS
= 

THIS WILL MAKE UPDATING TO NEW VERSIONS OF MRL MUCH EASIER. 
- The new chatbot will be tied to your ```data\config``` folder and not the current MRL version you are running.
- This way when you update to new versions, all you need to worry about is bringing your ```config``` folder over.

=======================================================

Find the chatbot you will want to clone in the ```MRL(version#)\resource\ProgramAB``` folder. Copy it!
- There are a number of different bots already there. Most of them are for different language support.
 - Choose the language you will be using.

In this case, I am using English and I copied ```en-US```. 

![Chatbots](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/b7a6cbe1-1ea2-4889-a43b-185fb875efc0)


Going back to the ```Custom``` folder I made earlier, I have also made a new folder in it called ```Chatbot```. 
- You can call things whatever you want. The file pathway is what we care about.

![CustomFolder1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/3d2338d4-a79d-43e1-a33d-c48d3ad787fb)


Paste the copied ```en-US``` folder into your ```Chatbot``` folder and rename it! Renaming the folder is IMPORTANT!
- I renamed mine ```Syntek``` as that is my robots name, name it whatever you would like. :)

After it is copy/pasted and renamed, we will ignore the folder for a few steps.

![CustomFolder2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/612ad804-ce7e-4c78-9ab5-41f937224e2b)

Now we will head back to your config folder ```MRL(ver)\data\config\``` and locate the ```i01.chatBot.yml```. 

![ServiceChatbot01](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f17b0c33-dfde-4c7b-92ec-b115ee0eea5e)

When you open up ```i01.chatBot.yml``` initially, it should look like this by default. 
- You can keep all the bots on the list or remove them as wanted.

Note: I had already changed mine, so I made a default ```i01.chatBot.yml``` in another config. 

![ChatbotDefaults](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/90d06cc3-6acc-4960-8637-3df8e757edf8)

ERROR WARNING:  If you are migrating your config folder over from a previous version of MRL, you may have an outdated ```i01.chatBot.yml```.

You will need to remove ```botDir: resource/ProgramAB``` from ```Line 2```.   ![botDirDeath](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2d3de592-83f1-41b6-9534-a082cf719b1b)

- This line can cause errors and needs to be removed from older versions of ```i01.chatBot.yml```.

Add the new location of your chatbot into the ```bot:``` list and save.

![CustomChatbot](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/2ce2b1e6-a2ef-40f0-9904-32b105cee369)

=======================================

Open MRL and start your config from runtime. Head over to the ```i01.chatBot``` tab and confirm your bots name is selected. 
- It should already be selected by default if you only had one chatbot in your ```i01.chatBot.yml```.
- It you have multiple chatbots, change it to whichever one you will be using when moving onto adding voice commands.

![SelectChatbot](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/88a1cd37-c9e0-4277-b27d-5aa185b74f32)

IF you had multiple chatbots: 
- Remember to first ```load and apply settings``` from ```python``` to avoid losing scripts included in ```python.yml``` prior to saving config.
- Save config from ```runtime```. (This will keep your new chatbot as the default when loading your config now). 

ADDING VOICE COMMANDS TO GESTURES
= 
Now we will return to our chatbot folder. ```MRL\Custom\Chatbot\Syntek\```

Within that folder we will be using a file named ```_inmoovGestures.aiml``` located within the ```aiml``` folder.     
  - Example location: ```MRL\Custom\Chatbot\Syntek\aiml\_inmoovGestures.aiml```

![CustomFolder3](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/f00025a0-dce7-417f-aa49-4d5637a2b271)

Here we can see an example of the format in which voice commands within ```_inmoovGestures.aiml``` will work. 
- ```CLOSE HANDS``` - will be the voice command said to the robot.
- ```Closing my hands.``` - Will be how the robot responds. (This is optional, you can leave it blank if you don't want a response.)
- ```handsclose()``` - is the defined gesture name. 

NOTE: What you say MUST match the command exactly. If in this example you said "Closed Hands", or "Close Hand" it will not work.
   - Unless of course you have made another command with that differently phrased voice command, or one already exists.

![AIML1](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/56f00773-f408-47c7-a6da-116543960cae)

Now we will add a new voice command of our own. I have placed this towards the bottom of the ```_inmoovGestures.aiml```.
- The new voice command must be located above the ```</aiml>``` at the bottom to work or not cause an error.

![AIML2](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/d57918db-ac97-4f38-be2e-cad04aac31ca)

You can use this as an outline if wanting and add it to your ```_inmoovGestures.aiml```.

```py
<category><pattern>TEST YOUR NECK FOR ME</pattern>
<template>Testing my neck.
        <oob><mrl><service>python</service><method>exec</method><param>examplescripttest1()</param></mrl></oob></template>
</category>
```

Don't forget to ```load and apply configuration``` to load your scripts prior to trying voice commands!
- They will not work if you haven't loaded your scripts yet!
- See IMPORTING YOUR GESTURES - ```load and apply configuration```. 

=======================================================


ADDITIONAL FUNCTIONS WITHIN GESTURES + NEED TO UPDATE LIST
= 

THINGS TO UPDATE 
- audioPeak for Jaw control + settings explained.
- audioFile? (Jaw responses to audio)
- audioPlayer? (Jaw does NOT respond to audio)
- Examples of Examples! Exploring the many other script examples available.


=======================================================

EXPLORING BUILT IN GESTURES
=
![DefaultGestures](https://github.com/CyberSyntek/i01-GesturesWithPython/assets/81597534/b3043a25-b057-473f-824c-b62567261de6)

InMoov built in gestures folder location.
- "myrobotlab-1.1.1402\resource\InMoov2\gestures"

You may want to explore this a bit and examine the various gesture examples you have available to you already. 

Keep in mind when I say explore, I mean examine the code rather then run them. 

- Some of the premade gestures are only partial gestures. They are not all made to run on their own. 
   - What this means is, one gesture might end in a position in which it was made to flow into another gesture. 
   - If you are running just the partial gesture, it may not end in a safe place if it can't flow to the next. 
   - Once autoDisable kills the power to certain servos, gravity may force them to come down on their own. (Risk of breaking something).

I'm planning on breaking that down a bit sometime near future and making a list to highlight the safe to run examples. 
- Some of them are safe as is, but I suggest you get used to reading the code before you run them so you can tell for yourself. 
- OR... wait for my list. :)
