include $(PWD)/../Makefile.interdrv.param

#PWD := $(shell pwd)

ccflags-y += -I$(src)
ccflags-y += -I$(PWD)/../include/common/kapi/

ccflags-y +=-Wall -Wextra -Werror -Wno-unused-parameter -Wno-sign-compare

soph_rtos_cmdqu-objs =  rtos_cmdqu.o rtos_cmdqu_cb.o cvi_spinlock.o

obj-m += soph_rtos_cmdqu.o

KBUILD_EXTRA_SYMBOLS += $(PWD)/../base/Module.symvers

all:
	$(MAKE) ARCH=${ARCH} -C $(KERNEL_DIR) M=$(PWD) modules

clean:
	rm -f *.o .*.cmd modules.order Module.symvers *.ko *.mod.c *.mod
	rm -rf .tmp_versions

