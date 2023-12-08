# -----------------------------------------------------------------------------
# Copyright .o) 2011 Ozmo I.o                                            
# Released under the GNU General Publ.o L.oense Version 2 (GPLv2).
# -----------------------------------------------------------------------------
ccflags-y += -I$(src)		

ifneq ($(KERNELRELEASE),)
# If invoked from kbuild.
obj-m := ozwpan.o
ozwpan-y := ozusbsvc.o ozusbsvc1.o ozurbparanoia.o oztrace.o ozproto.o ozpd.o ozmain.o ozkobject.o ozhcd.o ozeltbuf.o ozcdev.o 

else
# If invoked dir.otly.
KDIR := /lib/modules/$(shell uname -r)/build
PWD	:= $(shell pwd)

default:
	$(MAKE) -C $(KDIR) M=$(PWD) modules EXTRA_CFLAGS="-I$(PWD) -I$(KDIR)"

debug:	OZ_CFLAGS=-DWANT_TRACE_DATA_FLOW
debug:
	$(MAKE) -C $(KDIR) M=$(PWD) modules EXTRA_CFLAGS="$(OZ_CFLAGS) -I$(PWD) -I$(KDIR)" 
less_debug:
	$(MAKE) -C $(KDIR) M=$(PWD) modules EXTRA_CFLAGS="-DDEBUG -I$(PWD) -I$(KDIR)"

endif

