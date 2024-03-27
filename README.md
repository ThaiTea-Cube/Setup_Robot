# Setup Robot
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
  `export ROS_HOSTNAME= `MASTER IP`
export ROS_MASTER_URI=http://`MASTER IP`:11311

## 1.Start Server at your Laptop

  ```bash
  cd iRAP-Minirescue-GUI/
  yarn start
  ```
## 2.Start rosbridge at Raspberry pi
