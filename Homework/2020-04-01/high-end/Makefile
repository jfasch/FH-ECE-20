.PHONY: all clean help
all: greet-parameterized greet-simple
clean:
	rm greet-parameterized greet-simple *.o libgreet.a 
help:
	@echo "make VARIABLE=VALUE [VARIABLE=VALUE]"
	@echo "   Available variables:"
	@echo "   CROSS;   e.g. CROSS=arm-linux-gnueabihf"
	@echo "   SYSROOT; e.g. SYSROOT=/home/jfasch/cross/sysroots/raspberry"

SYSROOT_OPTION := $(if $(SYSROOT),--sysroot $(SYSROOT),)

%.o: %.c
	$(CROSS)-gcc $(SYSROOT_OPTION) -c -o $@ $<

libgreet.a: greet.o
	$(CROSS)-ar cq libgreet.a greet.o

greet-parameterized: greet-parameterized.o libgreet.a
	$(CROSS)-gcc $(SYSROOT_OPTION) -o greet-parameterized greet-parameterized.o libgreet.a

greet-simple: greet-simple.o libgreet.a
	$(CROSS)-gcc $(SYSROOT_OPTION) -o greet-simple greet-simple.o libgreet.a
