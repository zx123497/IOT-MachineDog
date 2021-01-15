# IOT Final Project --Machine Dog 
### ==107403525 資管3A 陳明昊==
![](https://i.imgur.com/6ihjn7K.jpg)

## Environments and Tools
### 1.Hardwares
* Raspberry Pi 3B
* PCA9685
* Servo Motor *2
* PIR
* Picamera v2
* 3.5mm Speaker
###  ==how to set your PCA9685==
* PCA9685 must have 6v power to let the servo motor to move successfully
* servo motor on the tail connect to PCA[0]
* servo motor on the mouth connect to PCA[1]
* first install the adafruit library
```
sudo pip3 install adafruit-circuitpython-servokit
```
![](https://i.imgur.com/TtlVzvK.png)
*  VCC connect to PIN1
* SDA connect to PIN3
* SCL connect to PIN5
* GND connect to PIN9

###  ==how to set your PIR==
*  VCC connect to PIN2
* GND connect to PIN6
* GPIO connect to PIN26

### 2.Environment
* Raspberry Os
* OpenCV 3.2.0
* GCC v7.1
* Python 3.7

###  ==how to build the OpenCV environment==
* Update the system
```
    sudo apt-get update
    sudo apt-get upgrade
    sudo rpi-update
    sudo reboot
```

* Install tools
```
    sudo apt-get install build-essential cmake cmake-curses-gui pkg-config vim
```
* Install Libraries
```
    sudo apt-get install \
      libjpeg-dev \
      libtiff5-dev \
      libjasper-dev \
      libpng12-dev \
      libavcodec-dev \
      libavformat-dev \
      libswscale-dev \
      libeigen3-dev \
      libxvidcore-dev \
      libx264-dev \
      libgtk2.0-dev
```

* v4l Library
```
    sudo apt-get -y install libv4l-dev v4l-utils
```

* activate core model
```
    sudo modprobe bcm2835-v4l2
```
* test the model
```
    v4l2-ctl --list-devices
```
* Other libraries
```
    sudo apt-get install libatlas-base-dev gfortran
```
 
* Install Python-Dev & Numpy
```
    sudo apt-get install python3-dev python3-numpy
```
* DownLoad OpenCV source packages
```
    mkdir /home/pi/Download/opencv
    cd  /home/pi/Download/opencv
    wget https://github.com/opencv/opencv/archive/3.2.0.zip -O opencv_source.zip
    wget https://github.com/opencv/opencv_contrib/archive/3.2.0.zip -O     opencv_contrib.zip
```
* unzip the code
```
    cd /home/pi/Download/opencv
    unzip opencv_source.zip
    unzip opencv_contrib.zip
```

* make build folder
```
    cd /home/pi/Download/opencv/opencv-3.2.0
    mkdir build
    cd build
```
* init the configuration and Cmake
```
    cmake -D CMAKE_BUILD_TYPE=RELEASE \
     -D CMAKE_INSTALL_PREFIX=/usr/local \
     -D BUILD_WITH_DEBUG_INFO=OFF \
     -D BUILD_DOCS=OFF \
     -D BUILD_EXAMPLES=OFF \
     -D BUILD_TESTS=OFF \
     -D BUILD_opencv_ts=OFF \
     -D BUILD_PERF_TESTS=OFF \
     -D INSTALL_C_EXAMPLES=ON \
     -D INSTALL_PYTHON_EXAMPLES=ON \
     -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-3.2.0/modules \
     -D ENABLE_NEON=ON \
     -D WITH_LIBV4L=ON \
        ../
```
* make build folder
```
    cd /home/pi/Download/opencv/opencv-3.2.0
    mkdir build
    cd build
```
* make build folder
```
    cd /home/pi/Download/opencv/opencv-3.2.0
    mkdir build
    cd build
```
* start building!!
```
    make -j4
```
* start installing and Finish!!
```
    sudo make install
    sudo ldconfig
```