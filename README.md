# Setup
## File
  ```
https://drive.google.com/file/d/1LEk0rXP_SjNGBCK9JZaAinB1yKYZ-NFf/view?usp=sharing
  ```
## yarn start at cd /iRAP-Minirescue-GUI
  ```bash
  yarn start
  ```
## rosbridge
  ```bash
  roslaunch rosbridge_server rosbridge_websocket.launch
  ```
## joy
  ```bash
  rosrun joy_controller joy_controller.py
  ```
## webcam
  ```bash
  roslaunch usb_cam two_usb_cams.launch
  ```
## arduino_serial
  ```bash
  rosrun rosserial_python serial_node.py /dev/ttyACM0
  ```
### For Check Camera detect
  ```bash
  rostopic echo /chatcam
  ```

# Setup Robot
### For control another PC on same network :
  ```bash
  ssh <name PC>@<Network IP>
  ```
## 0.When change wifi
for check your **MASTER IP** on Raspberry pi
  ```bash
  ifconfig
  ```
  change **MASTER IP** on Raspberry Pi and Laptop
  ```bash
  nano .bashrc
  ```
  at
  
  `export ROS_HOSTNAME= **MASTER IP**`
  
  `export ROS_MASTER_URI=http://**MASTER IP**:11311`

## 1.Start Server at your Laptop

  ```bash
  cd iRAP-Minirescue-GUI/
  yarn start
  ```
## 2.Start rosbridge at Raspberry pi
 ```bash
  roslaunch rosbridge_server rosbridge_websocket.launch
  ```
## 3.Start Joy controller[Sub and Pub] at Raspberry pi
 ```bash
  rosrun joy_controller joy_controller.py
  ```
## 4.Start Camera at Raspberry Pi
```bash
  roslaunch usb_cam two_usb_cams.launch
  ```
  
## 5.Start connecting Raspberry Pi and Arduino run at Raspberry pi
 ```bash
  rosrun rosserial_python serial_node.py /dev/ttyACM0
  ```
if port doesn't open run `sudo chmod a+rw /dev/ttyACM0`
