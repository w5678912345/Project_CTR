# Sources
SRC_DIR = . polarssl libyaml
OBJS = $(foreach dir,$(SRC_DIR),$(subst .c,.o,$(wildcard $(dir)/*.c)))

# Compiler Settings
LIBS = -static-libgcc
CXXFLAGS = -I.
CFLAGS = --std=c99 -O2 -flto -Wall -Wno-unused-but-set-variable -Wno-unused-value -Wno-unused-result -I. $(MAKEROM_BUILD_FLAGS)
CC = gcc
CXX = g++

# MAKEROM Build Settings
MAKEROM_BUILD_FLAGS = #-DDEBUG
OUTPUT = makerom

main: build

rebuild: clean build

build: $(OBJS)
	$(CXX) -o $(OUTPUT) $(LIBS) $(OBJS)

clean:
	rm -rf $(OUTPUT) $(OBJS) *.cci *.cia *.cxi *.cfa
