KERNEL_BUILD := /Volumes/FreeBASE/kernels/moto_razr
KERNEL_CROSS_COMPILE := arm-eabi-
EXTRA_CFLAGS :=
FILENAME := symsearch

obj-m += $(FILENAME).o
symsearch-y := search.o hijack.o

all:
	make -C $(KERNEL_BUILD) ARCH=arm CROSS_COMPILE=$(KERNEL_CROSS_COMPILE) M=$(PWD) modules
	$(KERNEL_CROSS_COMPILE)strip --strip-debug $(FILENAME).ko

clean:
	make -C $(KERNEL_BUILD) M=$(PWD) clean 2> /dev/null
	rm -f modules.order *~
