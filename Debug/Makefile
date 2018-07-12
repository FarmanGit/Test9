################################################################################
# Automatically-generated file. Do not edit!
################################################################################

### Toolchain: beaglebone_black-armv7l-timesys-linux-gnueabihf-gcc-5.5.0-20180313-03:03 ###
export CC=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-gcc
export STRIP=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-strip
export CXX=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-g++
export CPP=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-cpp
export RANLIB=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-ranlib
export DEBUGGER=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-gdb
export AR=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-ar
export AS=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-as
export OBJCOPY=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-objcopy
export OBJDUMP=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-objdump
export LD=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-ld
export NM=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-nm
export CROSS_COMPILE=/home/farman/timesys/beaglebone_black/toolchain/bin/armv7l-timesys-linux-gnueabihf-
export ARCH=arm

ROOT := ..

-include $(ROOT)/makefile.init

RM := rm -rf

PRODUCT = Test9_LKM
obj-m += $(PRODUCT).o
TS_C_OBJ_FILES := main.o
TS_S_OBJ_FILES :=
$(PRODUCT)-objs := $(TS_C_OBJ_FILES)  $(TS_S_OBJ_FILES)
TS_CFLAGS := -I$(PWD)/.. -I/home/farman/workspaces/TimeStorm-workspace/5.3.1/MR/WS11/Test8_LKP/include -Os -g3 -Wall -c -fmessage-length=0
TS_AFLAGS := 
EXTRA_LDFLAGS := 

CFLAGS_main.o := $(TS_CFLAGS)

TS_C_SOURCE_FILES := $(patsubst %.o, %.c, $(TS_C_OBJ_FILES))
TS_C_SOURCE_FILES += $(patsubst ../%.h, %.h, $(wildcard ../*.h))
TS_CLEAN_FILES := $(obj-m) \
	$(patsubst %.o,  %.mod.c, $(obj-m)) \
	$(patsubst %.o, %.mod.o, $(obj-m)) \
	$(patsubst %.o, %.ko, $(obj-m)) \
	$($(PRODUCT)-objs)
TS_CLEAN_FILES += \
	$(foreach file, $(filter %.o, $(TS_CLEAN_FILES)), $(join $(dir $(file)), $(patsubst %.o, .%.o.cmd, $(notdir $(file))))) \
	$(patsubst %.ko, .%.ko.cmd, $(filter %.ko, $(TS_CLEAN_FILES)))

-include $(ROOT)/makefile.defs

ifeq ($(KERNELRELEASE),)

$(TS_C_SOURCE_FILES): %: ../%
	 @ln -s $< $@


KDIR := /home/farman/workspaces/TimeStorm-workspace/5.3.1/MR/WS11/Test8_LKP
export PWD := $(shell pwd)
export PATH := $(PATH):/home/farman/timesys/beaglebone_black/toolchain/bin

all: print_toolchain $(TS_C_SOURCE_FILES) $(TS_S_SOURCE_FILES) callmake

callmake:
	 $(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules
	-@echo ' '


rmlinks:
	 rm -f $(TS_C_SOURCE_FILES) $(TS_S_SOURCE_FILES)

clean:
	rm -f $(TS_CLEAN_FILES) $(TS_C_SOURCE_FILES) $(TS_S_SOURCE_FILES)

rebuild: clean all


.PHONY : all clean rebuild callmake rmlinks print_toolchain

endif

-include $(ROOT)/makefile.targets

