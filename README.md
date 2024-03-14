# listadeponteiros
Resolução da lista de ponteiros
Nome: <Maria Letícia de Morais Ferreira e Karla Izabel Lima Rosendo>
Matricula: <20230022893 e 20230021368>

Questão 1:
<#include <stdio.h>

int main(void) {
  
  int i = 3,j = 5;
  int *p, *q;
  p = &i;
  q = &j;
  printf("p = %d, q = %d\n", *p, *q);
  p == &i;
  printf("O Resultado de p == &i é: %d\n", p == &i);
  // Por que o valor de p é 3, por isso quando colocamos o valor de p == &i, o resultado é 1.
  *p - *q;
  printf( "O Resultado de *p - *q é: %d\n", *p - *q);
  // O resultado de *p - *q é: -2, por que o valor de *p é 3 e o valor de *q é 5, então 3 - 5 é -2.
  **&p;
  printf( "O Resultado de **&p é: %d\n", **&p);
  // O resultado de **&p é: 3, por que o valor de **&p é o valor de *p, que é o valor de i, que é 3.
  3 - *p/(*q) + 7;
  printf( "O Resultado de 3 - *p/(*q) + 7 é: %d\n", 3 - *p/(*q) + 7);
  // O resultado de 3 - *p/(*q) + 7 é: 10, por que o valor de *p é 3, o valor de *q é 5, então 3 - 3 é 0, 0/5 é 0, 0 + 7 é 7.
  
  return 0;
}>
