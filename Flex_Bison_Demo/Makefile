.PHONY: clean

CC := gcc -std=gnu99
CFLAGS := -g

run: parser.tab.o scanner.o ast.o module.o main.o
	$(CC) -g -o $@ $+


clean:
	rm -f run *.o parser.tab* scanner.[ch] *.output

parser.tab.o: scanner.c

scanner.c: scanner.l
	flex --header-file=scanner.h --outfile=scanner.c scanner.l

parser.tab.c: parser.y
	bison -vd parser.y
