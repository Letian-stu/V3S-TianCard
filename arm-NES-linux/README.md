# V3S-TianCard 移植 NES 

```c
cd linux
1.
//修改joypad_input.cpp
//把/dev/input/event1 修改为你开发板的键盘设备 (可能是event0,event1,event2...)
#define KEYBOARD_DEV "/dev/input/event1" 
2.
修改makefile文件
//修改成自己电脑的gcc路径
CC = ~/Desktop/linux_stu/buildroot-2018.02.2/output/host/bin/arm-linux-gnueabihf-gcc	

//修改成自己电脑的路径
CCFLAGS =  -O2 -fsigned-char  -I/Desktop/linux_stu/buildroot-2018.02.2/output/staging/usr/include	
//修改成自己电脑的路径
LDFILGS = -lstdc++	-L/Desktop/linux_stu/buildroot-2018.02.2/output/staging/usr/lib	
//修改成自己电脑的路径
install ./InfoNES ~/Desktop/NES_Linux/arm-NES-linux-master/linux/work
```

