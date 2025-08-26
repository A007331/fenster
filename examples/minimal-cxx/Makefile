CXXFLAGS ?= -Wall -Wextra -std=c++11 -fno-rtti -fno-exceptions -g -Og

ifeq ($(OS),Windows_NT)
	LDFLAGS = -lgdi32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LDFLAGS = -framework Cocoa
	else
		LDFLAGS = -lxcb -lxcb-keysyms -lXau -lXdmcp
	endif
endif

main: main.cc ../../fenster.h
	$(CXX) main.cc -I../.. -o $@ $(CXXFLAGS) $(LDFLAGS)
