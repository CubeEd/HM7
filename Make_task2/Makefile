# Main Makefile

ifeq ($(USE_INCLUDE),1)
	include make1.mk
	include make2.mk
	include make3.mk
else
	MK_FILES = make1.mk make2.mk make3.mk
endif

.PHONY: all clean

all: main

main: main.o src1.o src2.o src3.o
	gcc main.o src1.o src2.o src3.o -o main 

main.o: main.c
	gcc -c main.c -o main.o

ifneq ($(USE_INCLUDE),1)
%.o:
	$(foreach mk, $(MK_FILES), $(MAKE) -f $(mk);)
endif

clean:
	rm -f *.o main
