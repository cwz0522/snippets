KDIR ?= /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)
modules clean help:
	$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) $@
