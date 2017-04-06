parse: pas_yacc.o pas_lex.o main.o 
	gcc -o parse pas_lex.o main.o pas_yacc.o

pas_lex.o: pas_lex.c
	gcc -c pas_lex.c

pas_lex.c: pas_lex.l
	flex -opas_lex.c pas_lex.l

pas_yacc.o: pas_yacc.c pascal.h
	gcc -c pas_yacc.c
	
pas_yacc.h: pas_yacc.y
	bison -d -opas_yacc.c pas_yacc.y
	
pas_yacc.c: pas_yacc.y
	bison -d -opas_yacc.c pas_yacc.y
	
main.o: main.c
	gcc -c main.c
	
clean:
	rm *.o pas_lex.c parse pas_yacc.c pas_yacc.h

# hidden rules
.c:	.l
	flex -o$< $@
