# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:Initiate the Mobile Robot.

<br/>

Step2:Connect your PC with Mobile robot through WIFI.

<br/>

Step3:Open batter_level.py file and check the battery.

<br/>

Step4:Open the other python file and program the movement of the robot using python.

<br/>

Step5:Execute the python program and record thr movement.

<br/>

## Program
```python

nimo spark
10:53 AM (11 hours ago)
to me

from robomaster import robot
from robomaster import camera
import time

if __name__ == '__main__':
    # Initialize robot connection
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    # Get robot modules
    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)

    # Movement and LED sequence
    sequence = [
        (2.3, 0, 0),
        (0.5, 0, 45),
        (0.5, 0, 30),
        (0.4, 0, 30),
        (0.4, 0, 45),
        (0.4, 0, 45),
        (0.7, 0, -35),
        (0.3, 0, 0),
        (0.6, 0, -45),
        (0.6, 0, 0),
        (0.3, 0, 45),
        (0.9, 0, 0),
        (0, 0, 55),
        (0.2, 0, -35),
        (0.4, 0, 45),
        (0.3, 0, 45),
        (0.8, 0, 0),
        (0.3, 0, 35),
        (0.1, 0, -45),
        (0.1, 0, 40),
        (0.2, 0, -30),
        (0.3, 0, 45),
        (0.4, 0, -25),
        (0, 0, 40),
        (0, 0, 5),
        (0.4, 0, 10),
        (0, 0, 0)
    ]

    for (x, y, z) in sequence:
        ep_chassis.move(x=x, y=y, z=z, xy_speed=1).wait_for_completed()
        ep_led.set_led(comp="all", r=255, g=100, b=0, effect="on")

    # Stop camera and close connection
    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

Insert image here


<br/>
<img width="910" height="380" alt="image" src="https://github.com/user-attachments/assets/fe4475f3-1947-4dd3-9a7e-ae1f11d4f239" />

<br/>
<br/>
<img width="971" height="412" alt="image" src="https://github.com/user-attachments/assets/346890bb-3d0d-4c6b-ba71-d4c608520f36" />

<br/>

## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here

https://youtu.be/Yp0fDy5ZyK0?si=6WsjZfbuNgx_ZzE5

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
