ligar = $(shell pkg-config --libs simavr)

compilar = $(shell pkg-config --cflags simavr)

.PHONY: all clean

all: simavr


simavr: simavr.o uart_pty.o
		gcc -o $@ $^ $(ligar) -lpthread -lutil


simavr.o: simavr.c uart_pty.h
		gcc -c simavr.c $(compilar)

uart_pty.o: uart_pty.c uart_pty.h
		gcc -c uart_pty.c $(compilar)

clean:
		rm -f *.o simavr
