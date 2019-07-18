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
we are the best

## ✍️ Project
this contain a project break down:

1. **pan-tilt movement with IMU:**
   1. **Hardware requirment:** Arduino, Wires, Breadboard, 3D Print Holder, Servo Motor(SG90), MPU6050
   1. **Software:** Arduino IDE
   1. **Wire:** Using `Circuit IO` to wire 
   1. **Implemention:** <br/>Use Arduino native example code `Servo` -> `Sweep` for servo control;<br/>Download IMU library from <a href="https://github.com/jrowberg/i2cdevlib/tree/master/Arduino"> i2cdevlib</a>, and copy `I2Cdev` and `MPU6050` folder into `Arduino` -> `Library` folder. relaunch arduino IDE and use example code `MPU6050_DMP6` for IMU control
   1. **Note:** <br/>base on different roll, pitch, yaw value on IMU, map the value to different motor, and control them base on the value change on IMU. 
1. **camera feedback with montion detection:**
   1. **Hardware requirment:** Arduino, Wires, Breadboard, 3D Print Holder, Servo Motor(SG90), MPU6050, `camera`, `OLED screen`.
   1. **Software:** Arduino IDE
   1. **wire:** Using `Circuit IO` to wire 
   1. **Implemention:** <br/>Go to Arduino IDER and click on `Sketch` -> `Include Library` -> `Manage Libraries`. Search for `adafruit ssd1306` and `adafruit gfx`. install them. relaunch arduino IDE, and use example code `Adafruit SSD1306` -> `ssd1306_128x32_i2c` for start.<br/>use native camera software you have on your PC to access camera feed. *(basic)*<br/> use python to write a <a href="https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_gui/py_video_display/py_video_display.html" >OpenCV</a> code to access camera *(advance)*
   1. **Note:** <br/>You can find basic of OLED on `PPT` folder. <br/>draw a face on OLED: use <a href="https://www.pixilart.com/draw" > Pixilart Website </a> to draw face. use different face drawing in the `loop` to animate the emotion.<br/> base on the angle change per second *(for example: if the data gap between each second is bigger than 40 degree in `yaw`, that means the person is saying "No", then you can make the OLED face turn to an angry emotion)* in roll, pitch, yaw *(as noding the head, shake the head)*, to change the face emotion on OLED. <br/> use <a href="https://www.amazon.com/Alvin-Wooden-Mannequin-Unisex-Inches/dp/B001OBMZIE/ref=sr_1_7?keywords=Wooden+Human+Mannequin&qid=1563489672&s=gateway&sr=8-7">human mannequin</a> to attach IMU and simulate human move.
1. **Arm control**<br>The concept will be the same as head control, you will need to add more motors and add one more IMUs to simulate the montion for each joints
   1. **Note:** <br/>find and 3d print a <a href="https://www.thingiverse.com/thing:90837" >3d servo arm model</a><br/> link IMU together, and look into example code on how to read date for two IMU
1. **Upper body control**<br/> this would bring the project into next level, a combination of all above work.
   1. **Note:** <br/> find and 3d print full humaiod robot <br/> link multi-IMU <br/> use <a href="https://www.amazon.com/HiLetgo-PCA9685-Channel-12-Bit-Arduino/dp/B01D1D0CX2/ref=asc_df_B01D1D0CX2/?tag=hyprod-20&linkCode=df0&hvadid=312106042452&hvpos=1o1&hvnetw=g&hvrand=4725520949653651188&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1023769&hvtargid=pla-439629573722&psc=1&tag=&ref=&adgrpid=62821668875&hvpone=&hvptwo=&hvadid=312106042452&hvpos=1o1&hvnetw=g&hvrand=4725520949653651188&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1023769&hvtargid=pla-439629573722"> multi-motor driver</a> to control multiple motors<br/> 






## 🎉 Resources <a name = "demo"></a>
|  |  |
| ---------- | ---------- |
| Free 3D printting: | <a href="https://www.thingiverse.com/">3D Printting Model Resource Link</a> <br/> <a href="https://www.thingiverse.com/thing:90837">Simple Robot Arms Model</a> |
| Arduino simulation:  | <a href="https://www.circuito.io/">Circuit IO</a> <br/> <a href="https://www.tinkercad.com/">Thinkercad</a>|
| Arduino hardware: | <a href="https://www.amazon.com/">Amazon (Online)</a> <br/> <a href="https://www.microcenter.com/">Micro Center (Online || Local Store)</a>|
| Linux: | <a href="https://ubuntu.com/">Ubuntu</a>|
| ROS: | <a href="http://wiki.ros.org/kinetic">ROS Kinetic (Ubuntu 16)</a> <br/> <a href="http://wiki.ros.org/melodic">ROS Melodic (Ubuntu 18)</a>|