# (ARM Cortex-M4F, XMC4500 Relax Kit, FreeRTOS w/Freertos+Plus, Linux Environment)
This repository contains projects done on ARM processor in linux environemnt.


###################################################################################################################################

## Project List ##

### 1. Demo project done in linux environment for ARM Cortex M4F

This demo project contains simple led blinking using Systick interrupt for every specific interval in C and C++ environment.
I have used some specific compilation flags for demo build but you can change it according to your convinience and wish.


### 2. FreeRTOS TCP/IP over Ethernet Porting on XMC4500 Relax Kit for Industrial/Automotive/IoT applications
It mainly focuses on FreeRTOS TCP/IP Server and Client application over Ethernet, CMSIS NN for Neural Networks(basics) using C/C++ for Industrial and IoT applications.

Porting of FreeRTOS+Plus done on XCM4500 over ethernet with applications. You can take it as a reference if you are utilizing FreeRTOS Network stack in your application. It would not take you much time to port SW on another interface by using this.

You can use it as a base for you project which uses ARM Cortex-M4F microcontroller utilizing FreeRTOS, FreeRTOS-Plus with C/C++.
Client and server test python script (rough) is also available to test the network.


###################################################################################################################################


You need ARM GNU toolchain for compilation and build which can be downloaded from ARM official website and JLink pack.

Version used - gcc-arm-none-eabi-7-2018-q2-update


Steps used to build executable using Makefile are as follows:

1. make all / make: build project executables
2. make clean:		clean the generated outputs
3. make flash:		start JLinkExe to flash the hex file


You can add includes/header files directories, sources and objects in sources.mk and objects.mk respectively which will be taken for build using build.mk and the finally executed by Makefile to generate the output.


First need to build the output files using make, for that enter,
$ make all: which will start compilation process and generate .elf, .hex, .lst and .map file and object files in DEBUG/Output folder

If anything goes wrong while building w.r.t. errors or warnings then clean the outputs and update source code
$ make clean

After updation again try to build the project
$ make


If successful, we can move to flashing the hex code in microcontrollers memory, for that,
$ make flash, you could have skipped make all/make and used make flash directly (totally depends on your wish)

If your device is connected to your system while executing make flash, it will start the JLinkExe and will ask you to type in commands for further process.
You do not need to fill the device information, it will be filled from Makefile itself.

JLink will prompt you to type connect, simply type connect as follows:
> connect, It will connect your device to host system. From here you can follow the further process.

Commands are as follows:

1. erase:		first erase the current flashed code from memory
> erase
2. loadfile:	load the hex file into controllers memory, do not need to fill memory address range or anything
> loadfile <filename.hex>
3. r:			reset and halts the target
> r
4. g:			start the CPU (go), which will start execution of your code on controller
> g
5. h:			halt the processor to see the CPU registers
> h
6. q:			quit the JLink session
> q

Using above steps you can load the hex file in microcontrollers memory and start the program.


Explore it, you will definitely like it.

Happy to Help and Share 😊

Cheers!!
