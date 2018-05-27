CC=gcc
WARNING_FLAGS=-Wall -Wextra -Wpedantic -Werror -Wno-unused-function
CFLAGS= -O2 -march=native $(WARNING_FLAGS) -std=gnu99 
DYLIBFLAGS=-dynamiclib -undefined suppress -flat_namespace

SOURCES=$(wildcard *.c) 
OBJECTS=$(patsubst %.c,%.o,$(wildcard *.c))
SHA3LIB=libshake.dylib


all: $(SOURCES) $(SHA3LIB)

$(SHA3LIB): $(OBJECTS)
	#ar rcs $@ $^
	$(CC) $(DYLIBFLAGS) $(OBJECTS) -o $@ 

.c.o: 
	    $(CC) -c $(CFLAGS) $< -o $@ $(LDFLAGS)

clean:
	rm *.o 2>/dev/null || true
	rm libkeccak.a 2>/dev/null || true
