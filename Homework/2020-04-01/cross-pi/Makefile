.PHONY: all clean
all: greet-parameterized greet-simple
clean:
	rm greet-parameterized greet-simple *.o libgreet.a 

greet.o: greet.c
	arm-linux-gnueabihf-gcc --sysroot $(HOME)/cross/sysroots/raspberry -c -o greet.o greet.c

greet-parameterized.o: greet-parameterized.c
	arm-linux-gnueabihf-gcc --sysroot $(HOME)/cross/sysroots/raspberry -c -o greet-parameterized.o greet-parameterized.c

greet-simple.o: greet-simple.c
	arm-linux-gnueabihf-gcc --sysroot $(HOME)/cross/sysroots/raspberry -c -o greet-simple.o greet-simple.c

libgreet.a: greet.o
	arm-linux-gnueabihf-ar cq libgreet.a greet.o

greet-parameterized: greet-parameterized.o libgreet.a
	arm-linux-gnueabihf-gcc --sysroot $(HOME)/cross/sysroots/raspberry -o  greet-parameterized greet-parameterized.o libgreet.a

greet-simple: greet-simple.o libgreet.a
	arm-linux-gnueabihf-gcc --sysroot $(HOME)/cross/sysroots/raspberry -o  greet-simple greet-simple.o libgreet.a
