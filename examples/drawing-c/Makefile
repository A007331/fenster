CFLAGS ?= -Wall -Wextra -std=c99 -g -Og

ifeq ($(OS),Windows_NT)
	LDFLAGS = -lgdi32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LDFLAGS = -framework Cocoa
	else
		LDFLAGS = -lxcb -lxcb-shm -lxcb-keysyms -lXau -lXdmcp
	endif
endif

main: main.c ../../fenster.h
	$(CC) main.c -I../.. -o $@ $(CFLAGS) $(LDFLAGS)
