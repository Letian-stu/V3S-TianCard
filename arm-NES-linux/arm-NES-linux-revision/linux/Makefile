CC = ~/Desktop/linux_stu/buildroot-2018.02.2/output/host/bin/arm-linux-gnueabihf-gcc

TARBALL = InfoNES08J

# InfoNES
.CFILES =	./../K6502.cpp \
		./../InfoNES.cpp \
		./../InfoNES_Mapper.cpp \
		./../InfoNES_pAPU.cpp \
		./InfoNES_System_Linux.cpp joypad_input.cpp

.OFILES	=	$(.CFILES:.cpp=.o)

CCFLAGS =  -O2 -fsigned-char  -I/Desktop/linux_stu/buildroot-2018.02.2/output/staging/usr/include
LDFILGS = -lstdc++	-L/Desktop/linux_stu/buildroot-2018.02.2/output/staging/usr/lib	# gcc3.x.x


all: InfoNES

InfoNES: $(.OFILES)
	$(CC) $(INCLUDES) -o $@ $(.OFILES) $(LDFILGS) -lm -lz -lpthread -lasound

.cpp.o:
	$(CC) $(INCLUDES) -c $(CCFLAGS) $*.cpp  -o $@

clean:
	rm -f $(.OFILES) ../*~ ../*/*~ core

cleanall:
	rm -f $(.OFILES) ../*~ ../*/*~ core InfoNES

release: clean all

tar:
	( cd ..; \
	tar cvf $(TARBALL).tar ./*; \
	gzip $(TARBALL).tar \
	)

install:
	install ./InfoNES ~/Desktop/NES_Linux/arm-NES-linux-master/linux/work
