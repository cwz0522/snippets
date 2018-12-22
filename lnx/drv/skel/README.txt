# Docs
	/usr/src/linux/Documentation/kbuild/kbuild.txt
	/usr/src/linux/Documentation/kbuild/makefiles.txt
	/usr/src/linux/Documentation/kbuild/modules.txt

# KBUILD_CFLAGS_MODULE   Options for $(CC) when building modules

	/usr/src/linux/arch/arm64/Makefile
		ifeq ($(CONFIG_ARM64_MODULE_CMODEL_LARGE), y)
		KBUILD_CFLAGS_MODULE	+= -mcmodel=large
		endif

# Option substitution
	/usr/src/linux/arch/arm/boot/compressed/Makefile
		ifeq ($(CONFIG_FUNCTION_TRACER),y)
		ORIG_CFLAGS := $(KBUILD_CFLAGS)
		KBUILD_CFLAGS = $(subst -pg, , $(ORIG_CFLAGS))
		endif

# Flags...
	/usr/src/linux/arch/arm64/Makefile
		LDFLAGS_vmlinux	:=-p --no-undefined -X
		CPPFLAGS_vmlinux.lds = -DTEXT_OFFSET=$(TEXT_OFFSET)
		GZFLAGS		:=-9

	/usr/src/linux/arch/arm/boot/compressed/Makefile
		AFLAGS_head.o += -DTEXT_OFFSET=$(TEXT_OFFSET)
