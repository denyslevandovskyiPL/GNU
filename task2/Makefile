MAINRULE = src2

ifdef env
ifeq (${env},2)
	MAINRULE = src1
endif
endif

all: ${MAINRULE}

src1: src1.o src2.o src3.o
	gcc main.c src1.o src2.o src3.o -o src
src2: compile.mk
	gcc main.c src1.o src2.o src3.o -o src

compile.mk:
	make -f make1.mk
	make -f make2.mk
	make -f make3.mk


.PHONY: clean all src

clean:
	rm -f *.o

clean-all: clean
	rm -f src

include make1.mk

include make2.mk

include make3.mk

