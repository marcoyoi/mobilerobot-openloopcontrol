# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

## Step1:

Define the predefined path
Create a list or array to store the coordinates of the robot's predefined path.
Each coordinate should represent a point along the path that the robot needs to follow.

## Step2:

Initialize the robot's starting position
Set the robot's initial position to the first coordinate in the predefined path.

## Step3:

Move the robot along the path
Loop through each coordinate in the predefined path, starting from the second coordinate.
Calculate the distance and direction from the robot's current position to the next coordinate.
Use appropriate robot control commands to move the robot towards the next coordinate.
Repeat this process for each coordinate in the predefined path.

## Step4:

Check if the robot has reached the end of the path
After completing the loop, compare the robot's final position with the last coordinate in the
predefined path.

If the two positions match or are within a certain threshold, the robot has successfully reached
the end of the path.
If not, modify the path or make other adjustments as needed.

## Step5:

End the program

Once the robot has reached the end of the path, stop the program or execute any additional
tasks required.
Print a message or perform any necessary cleanup steps before terminating the program.
## Program
```python
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)

    ep_chassis.move(x=2.5, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=0,effect="on")

    ep_chassis.move(x=0.4, y=0, z=67,xy_speed=1.1).wait_for_completed()
    ep_led.set_led(comp = "all",r=204,g=204,b=255,effect="on")

    ep_chassis.move(x=0.85, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=128,b=0,effect="on")

    ep_chassis.move(x=0, y=-1.4, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=102,b=0,effect="on")
    

    ep_chassis.move(x=0, y=0, z=102).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=204,b=0,effect="on")
    
    ep_chassis.move(x=0.6, y=0, z=-30, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=153,g=153,b=255,effect="on")
    
    ep_chassis.move(x=1.1, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")
     
    ep_chassis.move(x=0, y=0, z=130).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=0,b=0,effect="on")
    
    ep_chassis.move(x=0, y=1.55, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=10).wait_for_completed()
    ep_led.set_led(comp = "all",r=51,g=51,b=153,effect="on")

    ep_chassis.move(x=2.1, y=0, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=153,b=0,effect="on")

    ep_chassis.move(x=0, y=-0.6, z=0, xy_speed=1.3).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=128,b=128,effect="on")

    ep_chassis.move(x=0, y=0, z=440,xy_speed=1.3 ).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=255,b=0,effect="on")
    time.sleep(2)
    ep_led.set_led(comp = "all",r=255,g=0,b=0,effect="on")
    time.sleep(2)
    ep_led.set_led(comp = "all",r=255,g=0,b=255,effect="on")

    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![image](https://github.com/marcoyoi/mobilerobot-openloopcontrol/assets/128804366/67a416a8-c8f8-49bc-a9ca-ccc3c4dcb00b)


## MobileRobot Movement Video:

https://youtu.be/yeaJC8hq0SE?si=8RykZoWcOKxOS6k9

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
