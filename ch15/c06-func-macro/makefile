test: test.o libtio.a
	ld -m elf_i386 -o test test.o -L. -ltio

run: test
	./test

test.o: test.pcode test.funcmacro macro.inc
	nasm -f elf32 -P"macro.inc" -P"test.funcmacro" -o test.o test.pcode

libtio.a: tio.c
	gcc -m32 -c -o tio.o tio.c
	ar -crv libtio.a tio.o

clean:
	rm test.o test tio.o libtio.a
