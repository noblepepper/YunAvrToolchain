YunAvrToolchain
===============
This will allow Arduino sketches to be compiled and uploaded to the 32u4 side of the Yun from the AR9331 side with these caveats:

1. You need a sdcard set up by YunDiskSpaceExpander
2. You need to have installed unzip and make through opkg
3. You need to edit the sketch with a text editor of your choice
4. You need a makefile system like https://github.com/sudar/Arduino-Makefile/archive/master.zip, a Makefile to use Sudar's system is inlcuded in this package.
5. You must place function prototypes in your sketch before the function is called if you use any functions other than setup and loop

Installation Instructions:

1. Download this to your Yun with 

    wget https://github.com/noblepepper/YunAvrToolchain/archive/master.zip --no-check-certificate
    
    mkdir /usr/local
    
    mv master.zip /usr/local
    
    cd /usr/local
    
    unzip master.zip
    
    rm master.zip
    
2. Download a 1.5.x series Arduino IDE to your Yun with

    wget http://arduino.cc/download.php?f=/arduino-1.5.8-linux32.tgz --no-check-certificate
    
    mv download.php?f=/arduino-1.5.8-linux32.tgz /usr/local
    
    cd /usr/local
    
    tar zxvf download.php?f=/arduino-1.5.8-linux32.tgz
    
    rm download.php?f=/arduino-1.5.8-linux32.tgz
    
3. Download Sudar's makefiles with

    wget https://github.com/sudar/Arduino-Makefile/archive/master.zip --no-check-certificate
    
    mv master.zip /usr/local
    
    cd /usr/local
    
    unzip master.zip
    
    rm master.zip
    
4. Setup a work area and run a test

        mkdir /root/sketchbook
        
        cd /root/sketchbook
        
        cp -dpr /usr/local/arduino-1.5.8/examples/01.Basics/Blink ./
        
        cd Blink
        
        cp /usr/local/YunAvrToolchain-master/Makefile ./
        
        make
        
        merge-sketch-with-bootloader.lua build-yun/bridge.hex
        
        run-avrdude build-yun/bridge.hex


See https://github.com/noblepepper/toolchain-avr to see the changes from the stock Arduino toolchain that allowed this to be compiled on the Yun.

