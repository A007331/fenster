CFLAGS ?= -Wall -Wextra -std=c99

ifeq ($(OS),Windows_NT)
	LDFLAGS = -lgdi32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LDFLAGS = -framework Cocoa
	else
		# with FENSTER_XCB_USE_IMAGE 1
		#LDFLAGS = -lxcb -lxcb-image -lxcb-shm -lxcb-util -lxcb-keysyms -lXau -lXdmcp
		# with FENSTER_XCB_USE_IMAGE 0
		LDFLAGS= -lxcb -lxcb-keysyms -lXau -lXdmcp
		# partial static
		#LDFLAGS= -Wl,-Bstatic -lxcb -lxcb-keysyms -lXau -lXdmcp -Wl,-Bdynamic -Wl,--gc-sections
		# fully static (without TCP, getaddrinfo etc.)
		#LDFLAGS= -static -lxcb -lxcb-keysyms -lXau -lXdmcp
	endif
endif

main: main.c ../../fenster.h
	$(CC) main.c -I../.. -o $@ $(CFLAGS) $(LDFLAGS)
