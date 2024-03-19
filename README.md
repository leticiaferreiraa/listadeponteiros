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
-------------------------------------------------------------------------------------------------------------------------------------------------
Questão 2: 
<#include <stdio.h>

int main(void) {
  int i = 4094, *p;
  p = &i;
  printf(" O valor de i é = %d\n\n", i);
  printf("%p %p %d %d %d %d\n", p, p + 1, *p + 2, **&p, 3**p, **&p + 4);
  /* Nesse código, acontece algumas operações com ponteiros A partir disso, irá imprimir os seguintes valores:
%p: Endereço armazenado em p.
%p: Endereço resultante de p + 1.
%d: Valor apontado por p incrementado por 2.
%d: Valor apontado por *&p (equivalente a i).
%d: 3 multiplicado pelo valor apontado por p.
%d: Valor apontado por *&p incrementado por 4.
Depois de realizadas as operações, será imprimido o resultado na tela.*/

  return 0;
}>
----------------------------------------------------------------------------------------------------------------------------------------------------
Questão 3:
<#include <stdio.h>

int main(void) {
  int i=3,j=5;
  int *p, *q;
  q = &j; // Esse expressão está correta
  p = &i; // Esse expressão está correta
  // p = &*&i; Esse expressão está correta
  //*q = &j;// Esse expressão não está correta
  // i = (*&)j; Esse expressão não está correta
  // i = *&j; Esse expressão está correta
  // i = *&*&j;  Esse expressão está correta
  // q = *p; Esse expressão não está correta
  // i = (*p)++ + *q;  Essa expressão está correta

  printf("o valor é: %d\n", *p-*q);
  return 0;
}>
-----------------------------------------------------------------------------------------------------------------------------------------------------
Questão 4:
<#include <stdio.h>

int main(void) {

  int valor; 
  int *p1;
  float temp;
  float *p2;
  char aux;
  char *nome = "Ponteiros";
  char *p3;
  int idade;
  int vetor[3];
  int *p4;
  int *p5;
  
  /* (a) */
  valor = 10;
  p1 = &valor;
  *p1 = 20;
  printf(" %d\n ", valor);
// Nessa parte do código ele pega o número que está na variável "valor" e troca pelo número 20, através do ponteiro "*p1" depois ele imprime o resultado final.

  /* (b) */
  temp = 26.5;
  p2 = &temp;
  *p2 = 29.0;
  printf(" %.1f\n ", temp);
// Nessa parte do código ele pega o número que está na variável "temp" e troca pelo número 29.0, através do ponteiro "*p2", para depois ele imprimir o resultado final.
  
  /* (c) */
  p3 = &nome[0];
  aux = *p3;
  printf(" %c \n", aux);
  //Aqui usa ponteiro para imprimir a primeira letra da palavra "Ponteiros".

  /* (d) */
  p3 = &nome[4];
  aux = *p3;
  printf(" %c \n", aux);
  //Usando um ponteiro para imprimir a quinta letra da palavra "Ponteiros".

  /* (e) */
  p3 = nome;
  printf(" %c \n", *p3);
  //Aqui irá imprimir a primeira letra da palavra "Ponteiros".

  /* (f) */
  p3 = p3 + 4;
  printf(" %c \n", *p3);
  // Aqui irá avançar 4 posições e passará para o quinto caracter para depois imprimir a letra "e".

  /* (g) */
  p3--;
  printf(" %c \n", *p3);
  //Aqui irá voltar uma posição e imprimir a letra "o".

  /* (h) */
  vetor[0] = 31;
  vetor[1] = 45;
  vetor[2] = 27;
  p4 = vetor;
  idade = *p4;
  printf(" %d \n", idade);
  // Atribuindo os valores de um vetor a uma variável usando ponteiros e imprimindo o resultado logo depois.

  /* (i) */
  p5 = p4 + 1;
  idade = *p5;
  printf(" %d \n", idade);
  // Avança um ponteiro e imprime o próximo valor do vetor.

  /* (j) */
  p4 = p5 + 1;
  idade = *p4;
  printf(" %d \n", idade);
  // Avança mais um ponteiro e imprime o próximo valor do vetor

  /* (l) */
  p4 = p4 - 2;
  idade = *p4;
  printf(" %d \n", idade);
  // Volta dois valores do ponteiro e imprime o valor duas posições anteriores.

  /* (m) */
  p5 = &vetor[2] - 1;
  printf(" %d \n", *p5);
  // Define o ponteiro para o último valor do vetor e imprime o valor anterior.

  /* (n) */
  p5++;
  printf(" %d \n", *p5);
  // Avança o ponteiro e imprime o valor do vetor.
  
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------
Questão 5:
<#include <stdio.h>

int main(void){
  float vet[5] = {1.1,2.2,3.3,4.4,5.5};
//Aqui está criando um array de 5 posições com valores float.
  float *f;
//Declarando um ponteiro para um número de ponto flutuante.
  int i;
  f = vet;
// Atribuindo o endereço do primeiro elemento do array ao ponteiro.
  printf("contador/valor/valor/endereco/endereco\n");
// Imprimindo um cabeçalho para a tabela que será mostrada a seguir.
  for(i = 0 ; i <= 4 ; i++){
  printf("i = %d",i);
//Imprime o valor do contador.
  printf(" vet[%d] = %.1f",i, vet[i]);
// Imprime o valor do elemento do array na posição i, usando a notação de colchetes.
  printf(" *(f + %d) = %.1f",i, *(f+i));
// Imprime o valor do array, usando a aritmética de ponteiros.
  printf(" &vet[%d] = %X",i, &vet[i]);
// Imprime o endereço de memória do elemento no array usando o operador "&".
  printf(" (f + %d) = %X",i, f+i);
// Imprime o endereço de memória do elemento no array usando aritmética de ponteiros.
  printf("\n");
// Nesse código irá os valores do vetor e os endereços de memória de cada um deles, fazendo uma tabela disso.
  }
}>
---------------------------------------------------------------------------------------------------------------------------
Questão 6:
<#include <stdio.h>

int main(void) {
  int pulo[] = {1, 5, 10, 15, 20, 25};
  printf("*(pulo + 2): %d\n", *(pulo + 2));
  printf("*(pulo + 4): %d\n", *(pulo + 4));
  printf("pulo + 4 = %p\n", pulo + 4);
  printf("pulo + 2 = %p\n", pulo + 2);
// Ou seja, diante do resultado mostrado pelo programa. 
//A expressão que referencia o terceiro elemento do vetor é *(pulo + 2). 
//Já a expressão que referencia o quinto elemento do vetor é *(pulo + 4). 
//As outras expressões não são válidas, pois não são expressões aritméticas.
  return 0;
}>
-----------------------------------------------------------------------------------------------------------------------------
Questão 7:
<>
