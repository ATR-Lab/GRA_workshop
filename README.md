<p align="center">
  <a href="" rel="noopener">
 <img src="images/ATR-logo.gif" alt="ATR"></a>
</p>

<h3 align="center">GRA_workshop</h3>

<div align="center">

  [![Status](https://img.shields.io/badge/status-active-success.svg)]() 
  [![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

<p align="center"> this is an open source for GRA workshop
    <br> 
</p>

## 📝 About <a name = "about"></a>
This repository contains information and files relavent to the Grand River Academy's visit to the ATR Lab. 
ATR is a research laboratory focused on immersive robotics.



## 🏁 Project
Below is an overview of the project requirements:

### Arduino Project
**!!Hot Glue Can Sovle EVERYTHING!!**
1. **pan-tilt movement with IMU:**
   1. **Hardware requirment:** Arduino, Wires, Breadboard, 3D Print Holder, Servo Motor(SG90), MPU6050
   1. **Software:** Arduino IDE
   1. **Wire:** Using `Circuit IO` to wire 
   1. **Implemention:** <br/>Use Arduino native example code `Servo` -> `Sweep` for servo control;<br/>Download IMU library from <a href="https://github.com/jrowberg/i2cdevlib/tree/master/Arduino"> i2cdevlib</a>, and copy `I2Cdev` and `MPU6050` folder into `Arduino` -> `Library` folder. relaunch arduino IDE and use example code `MPU6050_DMP6` for IMU control
   1. **Note:** <br/>base on different roll, pitch, yaw value on IMU, <a href="https://www.arduino.cc/reference/en/language/functions/math/map/">map</a> the value to different motor, and control them based on the value change on IMU.

   **If you want to combine ROS with your project, you can jump to ROS Project from here** 

1. **camera feedback with montion detection:**<br/> Ignore `OLED` part if you dont have one.
   1. **Hardware requirment:** Arduino, Wires, Breadboard, 3D Print Holder, Servo Motor(SG90), MPU6050, `camera`, `OLED screen`.
   1. **Software:** Arduino IDE
   1. **wire:** Using `Circuit IO` to wire 
   1. **Implemention:** <br/>Go to Arduino IDER and click on `Sketch` -> `Include Library` -> `Manage Libraries`. Search for `adafruit ssd1306` and `adafruit gfx`. install them. relaunch arduino IDE, and use example code `Adafruit SSD1306` -> `ssd1306_128x32_i2c` for start.<br/>use native camera software you have on your PC to access camera feed. *(basic)*<br/> use python to write a <a href="https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_gui/py_video_display/py_video_display.html" >OpenCV</a> code to access camera *(advance)*
   1. **Note:** <br/>You can find basic of OLED on `PPT` folder. <br/>draw a face on OLED: use <a href="https://www.pixilart.com/draw" > Pixilart Website </a> to draw face. use different face drawing in the `loop` to animate the emotion.<br/> base on the angle change per second *(for example: if the data gap between each second is bigger than 40 degree in `yaw`, that means the person is saying "No", then you can make the OLED face turn to an angry emotion)* in roll, pitch, yaw *(as noding the head, shake the head)*, to change the face emotion on OLED. <br/> use <a href="https://www.amazon.com/Alvin-Wooden-Mannequin-Unisex-Inches/dp/B001OBMZIE/ref=sr_1_7?keywords=Wooden+Human+Mannequin&qid=1563489672&s=gateway&sr=8-7">human mannequin</a> to attach IMU and simulate human move.
1. **Arm control**<br>The concept will be the same as head control, you will need to add more motors and add one more IMUs to simulate the montion for each joints
   1. **Note:**<br/>find and 3d print a <a href="https://www.thingiverse.com/thing:90837" >3d servo arm model</a> **(you can come to ATR Lab with the model you find, we can print it for you)**<br/>if you dont want to do 3D print, you can use cardboard to make an holder yourself, or HOT GLUE them into each other.<br/> link IMU together, and look into example code on how to read date for two IMU<br/> you can use something like <a href="https://www.amazon.com/Alvin-Wooden-Mannequin-Unisex-Inches/dp/B001OBMZIE/ref=sr_1_9?keywords=Wooden+Human+Mannequin&qid=1563523009&s=gateway&sr=8-9">Wooden Human Mannequin</a> to attach your IMU for easy programming purpose.
1. **Upper body control**<br/> this would bring the project into next level, a combination of all above work.
   1. **Note:** <br/> find and 3d print full humaiod robot **(you can come to ATR Lab with the model you find, we can print it for you)**<br/>link multi-IMU <br/> use <a href="https://www.amazon.com/HiLetgo-PCA9685-Channel-12-Bit-Arduino/dp/B01D1D0CX2/ref=asc_df_B01D1D0CX2/?tag=hyprod-20&linkCode=df0&hvadid=312106042452&hvpos=1o1&hvnetw=g&hvrand=4725520949653651188&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1023769&hvtargid=pla-439629573722&psc=1&tag=&ref=&adgrpid=62821668875&hvpone=&hvptwo=&hvadid=312106042452&hvpos=1o1&hvnetw=g&hvrand=4725520949653651188&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1023769&hvtargid=pla-439629573722"> multi-motor driver</a> to control multiple motors<br/> 

### ROS Project
**ROS Project** part 1 and 2 is base on the **Arduino Project** part 1. and **ROS Project** part 3 is base on the **Arduino Project** part 2.
1. **read IMU data and servo control with terminal**
   1. **Note:** <br/>go through <a href="http://wiki.ros.org/rosserial/Tutorials">ros arduino</a> tutorial<br/> look into example `ros_lib` -> `pub_sub` and `ServoControl` 
1. **Remote control**<br/>Sperate IMU and motors into two arduino
   1. **Note:** <br/>use one arduino for sending IMU data through ROS, and another for receive data and control motor
1. **Camera view**
   1. **Note** <br/> Look into <a href="http://wiki.ros.org/cv_bridge/Tutorials/ConvertingBetweenROSImagesAndOpenCVImagesPython">OpenCV with ROS</a> for receive image view through ROS





## 🎉 Resources <a name = "demo"></a>
|  |  |
| ---------- | ---------- |
| Arduino: | <a href="https://www.arduino.cc/en/main/software">Ardiono IDE</a><br/><a href="https://www.arduino.cc/en/Tutorial/HomePage">Ardiono Tutorials</a><br/><a href="https://www.youtube.com/watch?v=BtLwoNJ6klE">Ardiono Basic (Video)</a><br/><a href="https://www.instructables.com/id/Arduino-How-to-Control-Servo-Motor-With-Arduino/">Servo Motor Example</a><br/><a href="https://www.hackster.io/Aritro/getting-started-with-imu-6-dof-motion-sensor-96e066">IMU Example</a><br/><a href="https://www.circuito.io/">Circuit IO (Arduino Wire Simulator)</a><br/><a href="https://www.tinkercad.com/">Thinkercad (Arduino Wire Simulator)</a><br/><a href="https://www.amazon.com/ELEGOO-Project-Starter-Tutorial-Arduino/dp/B01D8KOZF4/ref=sr_1_3?keywords=arduino&qid=1563520514&s=gateway&sr=8-3">Shopping: Arduino Parts (Amazon)</a> <br/> <a href="https://www.microcenter.com/search/search_results.aspx?Ntt=arduino&searchButton=search">Shopping: Arduino Parts (Micro Center Local Store)</a> |
| Ubuntu: | <a href="https://ubuntu.com/download/desktop">Ubuntu Download</a><br/><a href="https://www.youtube.com/watch?v=vt5Lu_ltPkU">Ubuntu Install (hard drive)</a><br/><a href="https://www.youtube.com/watch?v=QbmRXJJKsvs">Ubuntu Install (Virtual Machine on Windows)</a><br/><a href="https://www.youtube.com/watch?v=2v_3f_jjLL4">(What is Virtual Machine)</a><br/><a href="https://www.youtube.com/watch?v=Cvrqmq9A3tA">Ubuntu Install (Bash-Subsystem on Windows)</a><br/><a href="https://www.youtube.com/watch?v=lmeDvSgN6zY">Ubuntu Tutorial</a><br/><a href="https://www.youtube.com/watch?v=id3DGvljhT4">Command Line Tutorial</a><br/>|
| ROS: | <a href="http://wiki.ros.org/kinetic">ROS Kinetic Install (Ubuntu 16)</a> <br/> <a href="http://wiki.ros.org/melodic">ROS Melodic Install (Ubuntu 18)</a><a href="http://wiki.ros.org/ROS/Introduction">ROS Introduction</a> <br/><a href="http://wiki.ros.org/ROS/StartGuide">ROS Tutorials</a> <br/>|
| Free 3D printting: | <a href="https://www.thingiverse.com/">3D Printting Model Resource Link</a> <br/> <a href="https://www.thingiverse.com/thing:90837">Simple Robot Arms Model</a> |
| General: | <a href="https://www.youtube.com/watch?v=QXeEoD0pB3E&list=PLsyeobzWxl7poL9JTVyndKe62ieoN-MZ3">Python Tutorial</a>

## 🚀 Contact
Please feel free to contact atrlab.kent.help@gmail.com if you need any questions, or you can always drop by the lab between 12 am-5 pm.