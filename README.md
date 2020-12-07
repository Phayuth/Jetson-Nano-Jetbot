# Jetson-Nano-Jetbot
Jetson Nano Jetbot using some other electronic parts
![](https://github.com/Phayuth/Jetson-Nano-Jetbot/blob/main/Robot.jpg?raw=true)
## Requirement
### Hardware
1. 1 x [Nvidia Jetson Nano](https://cdn.antratek.nl/media/product/c93/nvidia-jetson-nano-developer-kit-945-13450-0000-100-fb6.jpg)
2. 1 x [Wifi Module](https://ae01.alicdn.com/kf/HTB1xtn8dhiH3KVjSZPfq6xBiVXay.jpg_q90.jpg)
3. 1 x [Motor Driver L298N](https://images-na.ssl-images-amazon.com/images/I/71kN49AetUL._SL1000_.jpg)
4. 4 x or 2 x [TT Motor](https://images-na.ssl-images-amazon.com/images/I/418YctAC26L.jpg)
5. 1 x [PCA9685 Board](https://images-na.ssl-images-amazon.com/images/I/61W%2BeG%2BLigL._AC_SX569_.jpg)
6. 1 x [Rasp pi Camera v2](https://cdn.shopify.com/s/files/1/0176/3274/products/std-camera_1024x.jpg?v=1540885797)
7. Battery for Motor Driver and Jetson Nano ( 12V )
8. Other accessories such as buck converter, wheels, bolts, nut, spacer nut, joystick controller,......
### Connection and Build
![](https://github.com/Phayuth/Jetson-Nano-Jetbot/blob/main/DIY%20Jetbot%20Connection.png?raw=true)
### Jetson Image Setup
1. Download Jetson nano image : https://drive.google.com/open?id=1G5nw0o3Q6E08xZM99ZfzQAe7-qAXxzHN
2. Boot the downloaded image to a SD card using Etcher
3. Insert the SD card into Jetson Nano
4. Bootup the Jetson Nano
### Configuration
On Jetson Terminal
```
$ sudo usermod -aG i2c jetbot
$ i2cdetect -y -r 1
```
The default PCA address should be 0X40. Thus we need to edit the address of the i2c in Adrafruit Library by Navigate to :
```
$ cd usr/local/lib/python
$ sudo gedit Adrafruit
```
Search for def _ _init_ _ (self,addr=0x60,freq=1600,i2c=none,i2c_bus=none):\
Change to def _ _init_ _ (self,addr=0x40,freq=1600,i2c=none,i2c_bus=none): and click save.
### The Robot should be remotely controllable via accessing Jupyter Notebook on browser
On another PC browser

1. Open Browser url bar access https://{jetbot_ip_address}:8888
2. Enter Jetbot Password "jetbot"
3. All the Notebook are ready to use
