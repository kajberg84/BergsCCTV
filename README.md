# SmartCCTV Camera - Build with a Raspberry Pi

## Preconditions

* Minimum Raspberry Pi 4, 2GB is recommended for optimal Face recognition performance
* [OpenCV face-recognition](https://github.com/ageitgey/face_recognition)
* Raspberry Pi 4 Camera Module or Pi HQ Camera Module (Newer version)
* Python 3 recommended.


## Step 1 – Install these dependencies

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install build-essential
    sudo apt-get install cmake
    sudo apt-get install gfortran
    sudo apt-get install git
    sudo apt-get install wget
    sudo apt-get install curl
    sudo apt-get install graphicsmagick
    sudo apt-get install libgraphicsmagick1-dev
    sudo apt-get install libatlas-base-dev
    sudo apt-get install libavcodec-dev
    sudo apt-get install libavformat-dev
    sudo apt-get install libboost-all-dev
    sudo apt-get install libgtk2.0-dev
    sudo apt-get install libjpeg-dev
    sudo apt-get install liblapack-dev
    sudo apt-get install libswscale-dev
    sudo apt-get install pkg-config
    sudo apt-get install python3-dev
    sudo apt-get install python3-numpy
    sudo apt-get install python3-pip
    sudo apt-get install zip
    sudo apt-get clean
    sudo apt-get install python3-picamera
    sudo pip3 install --upgrade picamera[array]

## Step 2 Increas SWAP file

    sudo nano /etc/dphys-swapfile
Change CONF_SWAPSIZE=100 to CONF_SWAPSIZE=1024 and save / exit nano

## Step 3 Install dlib

    mkdir -p dlib
    git clone -b 'v19.6' --single-branch https://github.com/davisking/dlib.git dlib/
    cd ./dlib
    sudo apt-get install cmake
    mkdir build; cd build; cmake .. ; cmake --build
    pip3 install dlib

## Step 4 Decrease SWAP file
    sudo nano /etc/dphys-swapfile
Change CONF_SWAPSIZE=1024 to CONF_SWAPSIZE=100 and save / exit nano

## Step 5 

    pip3 install numpy
    pip3 install scikit-image
    sudo apt-get install python3-scipy
    sudo apt-get install libatlas-base-dev
    sudo apt-get install libjasper-dev
    sudo apt-get install libqtgui4
    sudo apt-get install python3-pyqt5
    sudo apt install libqt4-test
    pip3 install opencv-python==3.4.6.27
    pip3 install face_recognition 

## Step 6 – Cloning SmartCCTV
Open up terminal and clone the SmartCCTV repo:


    bash cd /home/pi
    git clone https://github.com/EbenKouao/SmartCCTV-Camera


## Step 7 - Create Autostart on bootup

    bash cd modules
    sudo python3 /home/pi/SmartCCTV-Camera/main.py

## Step 8 - Enjoy