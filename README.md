# Prova
questão 3 da prova


#include <stdio.h>
#include <funcs.h>

int main()
{

int fatorial = 0; expoente = 0; escolha = 0;

printf("Digite 1 para prova ou 2 para expoente\n");
scanf("%d",&escolha);

if(escolha == 1){
  fatorial = func_fatorial();
  printf("O fatorial é : %d\n", fatorial);
}

if (escolha == 2){
  expoente= func_expoente();
  printf("O expoente é: %d\n", expoente);
}
}

int func_fatorial()
{
int num1 = 0;
printf("Digite um numero\n");
scanf("%d",&num1);
int cont = num1 - 1;

for(cont; cont>0; cont-1){
  num1 = num1 * cont;
}
return num1;
}

int func_expoente()
{
printf("Digite 2 numeros\n");
scanf("%d %d", &num1, &num2);
int num = 1;

for(num2; num2 > 1; num2--){
  num = num * num1;
  }
return num;
}


int func_expoente();
int func_fatorial();


CC=gcc
CFLAGS=-I.
DEPS = funcs.h
OBJ = main.o func_fatorial.o func_expoente.o
%.o: %.c $(DEPS)
$(CC) -c -o $@ $< $(CFLAGS)
prova: $(OBJ)
$(CC) -o $@ $^ $(CFLAGS)
clean:
rm -rf *o prova

