KDIR = /lib/modules/$(shell uname -r)/build

ifeq ($(RELEASE),1)
	BUILD = release
else
	BUILD = debug
endif

CLANG ?= clang
ifeq ($(origin CC),default)
CC := ${CLANG}
endif

all:
	$(MAKE) -C $(KDIR) M=$(CURDIR) CC=$(CC) BUILD=$(BUILD) CONFIG_CC_IS_CLANG=y

clean:
	$(MAKE) -C $(KDIR) M=$(CURDIR) CC=$(CC) clean
