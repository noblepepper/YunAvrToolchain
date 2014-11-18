YunAvrToolchain
===============
This will allow Arduino sketches to be compiled and uploaded to the 32u4 side of the Yun from the AR9331 side with these caveats:

1. You need to edit the sketch with a test editor of your choice
2. You must place function prototypes in your sketch if you use any functions other than setup and loop
3. You need a makefile system like https://github.com/sudar/Arduino-Makefile/archive/master.zip, a Makefile to use Sudar's system is inlcuded in this package.

See https://github.com/noblepepper/toolchain-avr to see the changes from the stock toolchain that allowed this to be compiled on the Yun.

