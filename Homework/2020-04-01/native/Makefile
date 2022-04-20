.PHONY: all clean
all: greet-parameterized greet-simple
clean:
	rm greet-parameterized greet-simple *.o libgreet.a 

greet.o: greet.c
	gcc -c -o greet.o greet.c

greet-parameterized.o: greet-parameterized.c
	gcc -c -o greet-parameterized.o greet-parameterized.c

greet-simple.o: greet-simple.c
	gcc -c -o greet-simple.o greet-simple.c

libgreet.a: greet.o
	ar cq libgreet.a greet.o

greet-parameterized: greet-parameterized.o libgreet.a
	gcc -o  greet-parameterized greet-parameterized.o libgreet.a

greet-simple: greet-simple.o libgreet.a
	gcc -o  greet-simple greet-simple.o libgreet.a
