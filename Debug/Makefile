ROOT := ..

-include Makefile.init

RM := rm -rf

PRODUCT = Test9LKM
obj-m += $(PRODUCT).o
TS_C_OBJ_FILES := main.o
TS_S_OBJ_FILES :=
$(PRODUCT)-objs := $(TS_C_OBJ_FILES)  $(TS_S_OBJ_FILES)
TS_CFLAGS := -I$(PWD)/.. -I/home/viky/workspaces/TimeStorm-workspace/5.3.2/RC1/LKP/include -Os -g3 -Wall -c -fmessage-length=0
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


KDIR := /home/viky/workspaces/TimeStorm-workspace/5.3.2/RC1/LKP
export KBUILD_OUTPUT := /home/viky/workspaces/TimeStorm-workspace/5.3.2/RC1/LKP/output
export PWD := $(shell pwd)
export PATH := $(PATH):/home/viky/timesys/nitrogen6x/toolchain/bin

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

