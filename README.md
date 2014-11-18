YunAvrToolchain
===============
This will allow Arduino sketches to be compiled and uploaded to the 32u4 side of the Yun from the AR9331 side with these caveats:

1. You need to edit the sketch with a test editor of your choice
2. You must place function prototypes in your sketch if you use any functions other than setup and loop
3. You need a makefile system like https://github.com/sudar/Arduino-Makefile/archive/master.zip, a Makefile to use Sudar's system is inlcuded in this package.

Installation Instructions:

1. Download this to your Yun with 

    wget https://github.com/noblepepper/YunAvrToolchain/archive/master.zip
    
    mkdir /usr/local
    
    mv master.zip /usr/local
    
    cd /usr/local
    
    unzip master.zip
    
    rm master.zip
    
2. Download a 1.5.x series Arduino IDE to your Yun with

    wget http://arduino.cc/download.php?f=/arduino-1.5.8-linux32.tgz
    
    mv arduino-1.5.8-linux32.tgz /usr/local
    
    cd /usr/local
    
    tar xvf arduino-1.5.8-linux.tgz
    
3. Download Sudar's makefiles with

    wget https://github.com/sudar/Arduino-Makefile/archive/master.zip
    
    mv master.zip /usr/local
    
    cd /usr/local
    
    unzip master.zip
    
    rm master.zip
    
4. Setup a work area and run a test
    mkdir /root/sketchbook
    cd /root/sketchbook
    cd sketchbook
    cp -dpr /usr/local/arduino-1.5.8/examples/01.Basics/Blink ./
    cd Blink
    cp 

See https://github.com/noblepepper/toolchain-avr to see the changes from the stock toolchain that allowed this to be compiled on the Yun.

