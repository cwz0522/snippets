export CONFIG_MY_DRV=m
export CONFIG_FOO_BAR=32

ifeq ($(KBUILD_OUTPUT),)
KDIR ?= /lib/modules/$(shell uname -r)/build
KDIR ?= ../../linux
else
KDIR ?= $(KBUILD_OUTPUT)/source
endif

MYDIR ?= ../../linux/drivers/foobar
EXTRA_SYMBOLS = $(MYDIR)

.PHONY: clean

modules clean help:
	$(MAKE) -C $(KDIR) M=$$PWD KBUILD_EXTRA_SYMBOLS="$(EXTRA_SYMBOLS)" $@

