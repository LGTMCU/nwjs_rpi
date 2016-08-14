NW.js port for Raspberry Pi 
---------------------------- 

[NW.js](http://nwjs.io/ "NW.js web site") (formely node-webkit) binary compiled for the ARMv6 used in Raspberry Pi. It also runs on Raspberry Pi 2 and Raspberry Pi 3 since they are backward compatible with ARMv6. Other compatible hardware could also run this binary althoguh it has not been tested yet.


## Instructions
1. **You need a package.nw** which is just a .zip file that contains your project (at least, it needs an index.html and a package.json). The included package.nw is just an example using [Yasminoku](https://github.com/jalbam/yasminoku "Yasminoku repository") game.

2. Optional: **merge nw and package.nw** into a single file with the following command:
	```
	cat nw package.nw > Your_new_binary_file
	```
	
3. **Edit fix_libudev.so.0 and fix_libudev.so.1** and replace Your_new_binary_file for the real name of your binary file (in the case you did not package nw and package.nw together, then your binary file is just nw).

4. In the case you need, **give executable permissions** (and other desired permissions) to Your_new_binary_file (or nw) using the **chmod** command.

5. In the case the system complains about libudev.so.0 just run:
	```
	./fix_libudev.so.0
	```
	Note: likewise, if needed, do the same for libudev.so.1 running **./fix_libudev.so.1**

6. If all works well, you can distribute your project. You will need these files at least (in the same folder): fix_libudev.so.0, fix_libudev.so.1, libffmpegsumo.so, nw.pak and Your_new_binary_file (or nw and package.nw instead).


## Versions
node-webkit (now called NW.js) version: v.0.7.0-pre
Node.js version: v0.10.12


## Tested on
* "Raspberry Pi Model B Revision 2.0 Mounting holes" with 512MB RAM (revision 000e) using Raspbian GNU/Linux 7 (wheezy) (Linux raspberrypi 4.1.19+ #858 armv6l GNU/Linux).
* "Raspberry Pi 3 Model B PCB Revision 1.2" with 1024MB RAM (revision a02082) using Raspbian GNU/Linux 8 (jessie) (Linux raspberrypi 4.1.19-v7+ #858 SMP armv71 GNU/Linux).


## Compatibility
* Raspberry Pi Zero, all models (untested)
* Raspberry Pi, all models
* Raspberry Pi 2, all models (untested)
* Raspberry Pi 3, all models
* Other devices with compatible hardware (untested)


## Credits:
Original binary was shared by [Nils M�s�n "piksel" (aka "spaculo")](https://github.com/piksel "NW.js web site") at <https://www.youtube.com/watch?v=MqNUYk9Y8jY> so thank you very much! :)