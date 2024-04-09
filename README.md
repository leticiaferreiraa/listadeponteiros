# listadeponteiros
Resolução da lista de ponteiros

Alunas: Maria Letícia de Morais Ferreira e Karla Izabel Lima Rosendo

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
  // O resultado de 3 - *p/(*q) + 7 é: 10, por que o valor de *p é 3, o valor de *q é 5, então 3 - 3 / 5  + 7. Ou seja, 3 - 0 + 7 = 10.
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------------------------------
Questão 2: 
<#include <stdio.h>

int main(void) {
  int i = 5, *p;
  p = &i;
  printf(" O valor de i é = %d\n\n", i);
  printf("%p %p %d %d %d %d\n", p, p + 1, *p + 2, **&p, 3**p, **&p + 4);
  /* Nesse código, acontece algumas operações com ponteiros.
A partir disso, irá imprimir os seguintes valores:
Portanto, supondo que a variável esteja na posição 4094, o resultado será:
i: Está na posição de memória 4094.
p = &i: 4094.
p+1: 4094 + 2 = 4096.
*p+2: Aqui pegará o valor apontado por p que no caso é = 5, acrescentando mais 2. Ou seja, 5 + 2 = 7.
**&p: Valor que é o mesmo que i = 5.
3**p: 3 multiplicado pelo valor apontado por p, que é 5, resultando em 3 * 5 = 15.
**&p+4: O valor apontado por *&p (que é i) somado a 4, ou seja, 5 + 4 = 9.*/

  return 0;
}>
----------------------------------------------------------------------------------------------------------------------------------------------------
Questão 3:
<#include <stdio.h>

int main(void) {
  int i=3,j=5;
  int *p, *q;
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
  // Ou seja, o primeiro elemento do vetor que será impresso na tela.
  
  /* (i) */
  p5 = p4 + 1;
  idade = *p5;
  printf(" %d \n", idade);
  // Avança uma posição, imprimindo assim, o próximo valor do vetor.
  
  /* (j) */
  p4 = p5 + 1;
  idade = *p4;
  printf(" %d \n", idade);
  // Aqui também irá avançar mais uma posição, consequentemente imprime o próximo valor.
  
  /* (l) */
  p4 = p4 - 2;
  idade = *p4;
  printf(" %d \n", idade);
  // Volta em duas posições e imprime o valor.
  
  /* (m) */
  p5 = &vetor[2] - 1;
  printf(" %d \n", *p5);
  // Define o ponteiro para o último valor do vetor, consequentemente voltando uma posição.
  
  /* (n) */
  p5++;
  printf(" %d \n", *p5);
  // Pega a posição que o vetor estáe avança, assim imprimindo o valor.
  
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------
Questão 5:
<#include <stdio.h>
int main(void){
  float vet[5] = {1.1,2.2,3.3,4.4,5.5};
//Aqui está criando um array de 5 posições com valores float.
  float *f;
  int i;
  f = vet;
// Atribuindo o endereço do primeiro elemento do array ao ponteiro.
  printf("contador/valor/valor/endereco/endereco\n");
// Imprimindo um cabeçalho para a tabela que será mostrada a seguir.
  for(i = 0 ; i <= 4 ; i++){
  printf("i = %d",i);
//Imprime o valor do contador.
  printf(" vet[%d] = %.1f",i, vet[i]);
// Imprimindo o valor do elemento do vetor na posição i.
  printf(" *(f + %d) = %.1f",i, *(f+i));
// Imprimindo o valor do vetor, usando uma soma com os ponteiros.
  printf(" &vet[%d] = %X",i, &vet[i]);
// Imprime o endereço de memória do elemento usando o operador "&".
  printf(" (f + %d) = %X",i, f+i);
// Imprime o endereço de memória do elemento usando a soma com ponteiros.
  printf("\n");
// Ou seja, esse código faz uma tabela com os valores do vetor definido e os endereços de memória de cada um deles.
  }
}>
---------------------------------------------------------------------------------------------------------------------------
Questão 6:
<#include <stdio.h>
int main(void) {
  int pulo[] = {1, 5, 10, 15, 20, 25};
  printf("*(pulo + 2): %d\n", *(pulo + 2));
// Referencia o valor do terceiro elemento do vetor pulo[].
  printf("*(pulo + 4): %d\n", *(pulo + 4));
// Referencia o valor do quinto elemento do vetor pulo[].
  printf("pulo + 4 = %p\n", pulo + 4);
  printf("pulo + 2 = %p\n", pulo + 2);
// Nessas outras duas impressões são mostradas as posições de memória.
  return 0;
}
Já que o primeiro elemento do array é representado pelo número zero.>
-----------------------------------------------------------------------------------------------------------------------------
Questão 7:
<#include <stdio.h>
int main(void) {
  int mat[4], *p, x;
//Aqui está sendo atribuidos valores para os elementos da matriz
  mat[0] = 1;
  mat[1] = 2;
  mat[2] = 3;
  mat[3] = 4;
  p = mat + 1; 
// Essa expressão é válida. Ou seja, o p aponta para o segundo elemento da matriz "mat".
  //p = mat;
// Essa expressão é válida. Ou seja, o p aponta para o primeiro elemento da matriz "mat".
 // *p = mat;
// Essa expressão é inválida. Ou seja, ela mudará o valor de mat como é um ponteiro.
  x = (*mat);
// Essa expressão é válida. Ou seja, o "*mat" é equivalente ao "mat[0]". Por isso, aponta para o primeiro elemento da matriz.
 printf("Valor de mat[0]: %d\n", mat[0]);
 printf("Valor de mat[1]: %d\n", mat[1]);
 printf("Valor de mat[2]: %d\n", mat[2]);
 printf("Valor de mat[3]: %d\n", mat[3]);
  printf("Valor de p: %d\n", *p);
  printf("Valor de x: %d\n", x);  
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------------
Questão 8:
<#include <stdio.h>
int main(void) {
  int vet[] = {4, 9, 13};
  int i;
// Essa condição fica responsável por percorrer o vetor, assim, imprimindo os elementos logo em seguida.
  for(i = 0;i < 3;i ++){
  printf("%d \n", *(vet+i));
  }
// O programa em C imprime todos os valores do vetor definido.
  return 0;
}
#include <stdio.h>
int main(void) {
  int vet[] = {4, 9, 13};
  int i;
// Essa condição fica responsável por percorrer o vetor, assim, imprimindo os elementos logo em seguida.
  for(i = 0;i < 3;i ++){  
  printf("%X ", vet+i);
// Esse printf não irá imprimir o valor de cada posição do vetor. Pois, o vetor não está representado corretamente, aqui está aparecendo a posição de memória de cada um.
  }
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------------------------------
Questão 9:
<#include <stdio.h>
struct teste{
  int x = 3;
  char nome[] = "jose";
};
int main(void) {
  struct teste *s;
  printf("%d", s-> x);
  printf("%s", s-> name);
}
  return 0;
// O programa não será compilado, pois não é possível encontrar o valor de x e nem o nome. Pois, existe erros de definições das estruturas das variáveis presentes no código.
}>
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 10:
<#include <stdio.h>
int main(void) {
  int const *x = 3;
// Declarando um ponteiro constante 3.
  printf("%d", ++ (*x));
// Como não é permitido um valor inteiro para uma variável constante, o código não roda e exibirá a mensagem de erro.
  return 0;
}>
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 11:
<#include <stdio.h>

int main(void) {
  char x1[4];
  int x2[4];
  float x3[4];
  double x4[4];
   printf("Aqui será mostrado os endereços de memória dos elementos de x:\n");
   printf("char:   %p\n", (void*) &x1[0]);
   printf("int:    %p\n", (void*) &x2[0]);
   printf("float:  %p\n", (void*) &x3[0]);
   printf("double: %p\n", (void*) &x4[0]);
   printf("\nAqui será mostrado os endereços de memória de x+1, x+2 e x+3:\n");
   printf("char:   %p %p %p\n", (void*) (x1 + 1), (void*) (x1 + 2), (void*) (x1 + 3));
   printf("int:    %p %p %p\n", (void*) (x2 + 1), (void*) (x2 + 2), (void*) (x2 + 3));
   printf("float:  %p %p %p\n", (void*) (x3 + 1), (void*) (x3 + 2), (void*) (x3 + 3));
   printf("double: %p %p %p\n", (void*) (x4 + 1), (void*) (x4 + 2), (void*) (x4 + 3));
// Esse programa irá imprimir na tela, para o usuário, os endereços de memória dos elementos de cada vetor. Logo em seguida, irá imprimir os endereços de memória de x+1, x+2 e x+3. Sendo todas as impressões para cada tipo de dado.
  return 0;
}>
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Questao 12:
  <#include <stdio.h>
  
  int main(void) {
  float aloha[10], coisas[10][5], *pf, value = 2.2;
  int i=3;
  aloha[2] = value; // Comando Válido, ou seja o programa irá imprimir um valor de 2.20000
  scanf("%f", &aloha);// Comando Válido, ou seja irá escrever um valor em float na variável
  aloha = "value";//Inválido pois não é possível guardar uma string a um array de floats
  printf("%f", aloha);//Inválido pois não é possível imprimir um array de floats
  coisas[4][4] = aloha[3]; //Comando Válido
  coisas[5] = aloha;//Inválido, pois não é possível atribuir valores
  pf = value;// Inválido pois não é possível atribuir o value a um ponteiro de float 
  pf = aloha; //Comando Válido.
  return 0;}>
----------------------------------------------------------------------------------------------------------
Questão 13:
</A memory leak, é um vazamento de memória, ocorre quando o programa não libera para o sistema operacional memória que não é mais utilizada. Ou seja, irá ter um consumo cada vez maior da memória da máquina. O problema surge a partir do gerenciamento na alocação dinamica. As funções usadas são o malloc() e calloc(), elas alocam memórias para o programa, que depois são liberadas.
  Exemplos:
  1-
  #include <stdlib.h>
  int main() {
    int *ptr = (int *)malloc(sizeof(int));
    // Usando ptr para outras operações sem liberar a memória alocada
    return 0;
}
Neste exemplo, malloc() é usado para alocar memória dinamicamente para um inteiro. No entanto, depois de usar a variável ptr, a memória alocada não é liberada usando free(ptr). Isso resulta em um vazamento de memória, pois a memória alocada dinamicamente não é mais acessível, mas ainda está ocupando espaço na memória.
2-
#include <stdlib.h>
int main() {
    int *ptr = (int *)malloc(sizeof(int));
    ptr = NULL; // Perdendo a referência para a memória alocada
    return 0;
}
Neste caso, a memória é alocada dinamicamente para um inteiro e armazenada em ptr. No entanto, em seguida, o ponteiro ptr é definido como NULL, resultando na perda da referência para a memória alocada. Isso significa que não há mais maneira de acessar ou liberar essa memória, resultando em um vazamento de memória.
3- 
#include <stdlib.h>
void recursiveFunction(int n) {
    int *ptr = (int *)malloc(sizeof(int));
    if (n > 0) {
        recursiveFunction(n - 1);
    }
    // Esquecendo de liberar ptr
}
int main() {
    recursiveFunction(5);
    return 0;
}
Por último, neste exemplo, uma função recursiva recursiveFunction é usada para alocar memória dinamicamente em cada chamada recursiva. No entanto, a memória alocada em cada chamada não é liberada antes de retornar da função. Isso pode levar a um vazamento de memória, especialmente se a recursão for profunda ou se o loop for executado muitas vezes, consumindo mais memória alocada dinamicamente a cada iteração.>
-------------------------------------------------------------------------------------------------------------------------------------------------------------
Questao 14: 
<O uso de ponteiros para funções em C serve principalmente para definir, em tempo de execução,
qual função será executada, sem a necessidade de escrever o nome da função, de forma explícita naquele ponto do código.
Exemplo:
#include <stdio.h>
void main()
{
  int a;     //declara a variável a como inteiro 
  int b;     //declara a variável b como inteiro
  int c;     //declara a variável c como inteiro
  int *ptr;  // declara um ponteiro para um inteiro
             // um ponteiro para uma variável do tipo inteiro
  a = 90;    // esse valor será apontado no ponteiro
  b = 2;     // valor de b
  c = 3;     // valor de c 
  ptr = &a;  // ptr recebe o endereço de a
  printf("Endereço de ptr: %p, Conteúdo do ptr de a: %d\n", ptr, *ptr);// mostra o endereço de ptr e o conteúdo de ptr de a
  printf("B: %d, C: %d", b, c);
}>
----------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 15:
<#include <stdio.h>
#include <stdlib.h>
float ordenar (float *array, int n) {
    int i, j;
    float temp;
    for (i = 0; i < n - 1; i++) 
    {
        for (j = 0; j < n - i - 1; j++){
            if (array[j] > array [j + 1]) {
                temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }
}
int main(void) {
    int i, n;
    float *ordem;
    printf("Digite a quantidade de valores a serem ordenados: ");
    scanf("%d", &n);
  float valores[n];
  printf( "Digite os valores a serem ordenados: \n");
  for (i = 0; i < n; i++){
    scanf("%f", &valores[i]);
  }
    ordem = malloc(n * sizeof(float));
    if (ordem == NULL) {
        printf("Erro de alocação de memória");
        return 1;
    }
    for (i = 0; i < n; i++) {
        ordem[i] = valores[i];
    }
    ordenar(ordem, n);
    printf("Mostrando que a ordem crescente dos valores são:\n");
    for (i = 0; i < n; i++) {
        printf("%f\n", ordem[i]);
    }
    free(ordem);
    return 0;
}>
---------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 16:
<#include <stdio.h>
#include <stdlib.h>
//Função de comparação para o qsort
int compare(const void* p1, const void* p2){
  //Converte os ponteiros para inteiros
  if( *(int*)p1 < *(int*)p2){
    return -1;
  }
  //Se os valores forem iguais, retorna 0
  if( *(int*)p1 == *(int*)p2){
    return 0;
  }
  //Se os valores forem diferentes, retorna 1
  if( *(int*)p1 > *(int*)p2){
    return 1;
  }
}
int main(void) {
    int i, n;
    float *ordem;
    printf("Digite a quantidade de valores a serem ordenados: ");
    scanf("%d", &n);
  float valores[n];
  printf( "Digite os valores a serem ordenados: \n");
  //Leitura dos valores 
  for (i = 0; i < n; i++){
    scanf("%f", &valores[i]);
  }
//Aloca memória para o vetor de ponteiros
    ordem = malloc(n * sizeof(float));
  //Copia os valores do vetor de float para o vetor de ponteiros
    if (ordem == NULL) {
 //Se a alocação de memória falhar, exibe uma mensagem de erro e encerra o programa
        printf("Erro de alocação de memória");
        return 1;
    }
  //Copia os valores do vetor de float para o vetor de ponteiros
    for (i = 0; i < n; i++) {
        ordem[i] = valores[i];
    }
  //Ordena o vetor de ponteiros usando a função qsort, que foi usada através da função compare
    qsort(valores, n, sizeof(float), compare);
    printf("Mostrando que a ordem crescente dos valores são:\n");
    for (i = 0; i < n; i++){
        printf("%f\n", valores[i]);
    }
  //Libera a memória alocada
    free(ordem);
    return 0;
}>
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 17:
<#include <stdio.h>
#include <stdlib.h> 
int compare(const void* p1, const void* p2){
  if( *(int*)p1 < *(int*)p2){
    return -1;
  }
  if( *(int*)p1 == *(int*)p2){
    return 0;
  }
  if( *(int*)p1 > *(int*)p2){
    return 1;
  }
}
int main(void){
  int x[] = {5, 19, 21, 10, -89};
  int i;
  printf("Os valores inteiros são: \n");
  for(i=0; i<5; i++){
    printf("%d ", x[i]);
  }
  printf("\n\n");
  qsort(x, 5, sizeof(int), compare);
   printf("Os valores inteiros em ordem crescente são: \n");
  for(i=0; i<5; i++){
    printf("%d ", x[i]);
  }
}>
----------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 18:
<#include <stdio.h>
#include <time.h>
// Função de ordenação bubble sort
void bubble_sort(int arr[], int n) {
    // implementação do algoritmo bubble sort
}
int main() {
    // Array de exemplo e tamanho
    int arr[] = {5, 2, 7, 1, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    // Medição do tempo de execução
    clock_t start, end;
    double cpu_time_used;
    start = clock(); // inicia a contagem de tempo
    bubble_sort(arr, n); // chamada da função de ordenação
    end = clock(); // finaliza a contagem de tempo
    cpu_time_used = ((double) (end - start)) / CLOCKS_PER_SEC;
    printf("Tempo de execução: %f segundos\n", cpu_time_used);
     return 0;
     }
Usando funções de data e hora do sistema: 
Em Unix, uma função comum é gettimeofday() ou clock_gettime(). Em Windows, pode-se usar GetSystemTime() ou QueryPerformanceCounter(). A diferença entre os tempos antes e depois da execução da rotina dá uma medida do tempo de execução. É usado a biblioteca <time.h>: Esta biblioteca fornece funções como clock() para medir o tempo de CPU consumido pela execução de um programa. O tempo retornado é dado em "ticks de clock", e pode ser convertido para segundos usando a macro CLOCKS_PER_SEC.
Ou seja, pode então concluir qual implementação é mais eficiente em termos de tempo de execução para o conjunto de dados e o ambiente de execução específicos.>
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Questão 19:
<#include <stdio.h>
#include <stdlib.h>
void soma_vet(int *vet1, int *vet2, int *result, int tam) {
//Condição criada para a realização da soma dos vetores.
    for (int i = 0; i < tam; i++) {
        *(result + i) = *(vet1 + i) + *(vet2 + i);
    }
}
int main() {
    int tam;
    printf("Olá, digite aqui qual será o tamanho do vetor desejado: ");
    scanf("%d", &tam);
    // Alocando uma memória para os vetores
    int *vet1 = (int *)malloc(tam * sizeof(int));
    int *vet2 = (int *)malloc(tam* sizeof(int));
    int *result = (int *)malloc(tam * sizeof(int));
    printf("Digite aqui os elementos do primeiro vetor:\n");
    for (int i = 0; i < tam; i++) {
        scanf("%d", vet1 + i);
    }
    printf("Digite aqui os elementos do segundo vetor:\n");
    for (int i = 0; i < tam; i++) {
        scanf("%d", vet2 + i);
    }
    soma_vet(vet1, vet2, result, tam);
    printf("Resultado da soma dos vetores:\n");
    for (int i = 0; i < tam; i++) {
        printf("%d ", *(result + i));
    }
    free(vet1);
    free(vet2);
    free(result);
    return 0;
  }>
  ------------------------------------------------------------------------------------------------------------------------------
  Questão 20:
  <#include <stdio.h>
#include <stdlib.h>

int multiplica_matrizes(int **A, int **B, int **C, int nl, int nc, int nc2){
for (int i = 0; i < nl; i++) {
    for (int j = 0; j < nc2; j++) {
        C[i][j] = 0;
        for (int k = 0; k < nc; k++) {
            C[i][j] += A[i][k] * B[k][j];
        }
    }
}
}
int main(void) {

  int **A, **B, **C, nl =2, nc = 3, i, j;
  int nl2 =3, nc2 = 4;
  int nlz, ncz;

  A = (int **) malloc(nl*sizeof(int *));
  for (i=0; i<nl; i++){
    A[i] = (int *) malloc(nc*sizeof(int));
}
    B = (int **) malloc(nl*sizeof(int *));
    for (i=0; i<nl; i++){
      B[i] = (int *) malloc(nc*sizeof(int));
  }
    C = (int **) malloc(nl*sizeof(int *));
    for (i=0; i<nl; i++){
      C[i] = (int *) malloc(nc*sizeof(int));
  }

  for(i=0; i<nl; i++){
    for (j=0; j<nc; j++){
      A[i][j] = i+j;
    }
  }
  for(i=0; i<nl; i++){
    for (j=0; j<nc; j++){
      B[i][j] = i+j;
    }
  }
  for(i=0; i<nl; i++){
    for (j=0; j<nc; j++){
      C[i][j] = i+j;
    }
  }
  multiplica_matrizes(A,B, C, nl,nc, nc2);
  printf("Resultado da multiplicação das matrizes:\n");
  for (int i = 0; i < nl; i++) {
      for (int j = 0; j < nc2; j++) {
          printf("%d ", C[i][j]);
      }
      printf("\n");
  }

  for(i=0; i<nl; i++){
    free(A[i]);
  }
free(A);

  for(i=0; i<nl; i++){
      free(B[i]);
    }
  free(B);
  for(i=0; i<nl; i++){
      free(C[i]);
    }
  free(C);
  return 0;
}>
  -------------------------------------------------------------------------------------------------------------------------------
  Questão 21:
  <A void f( ){
  void *s;
  s = malloc(50);
  free(s);
}
B int f( ){
  float *a;
  return 0;
}
C int f(char *data){
  void *s;
  s = malloc(50);
  int size = strlen(data);
  if (size > 50)
  return(-1);
  free(s);
  return 0;
}
D int *f(int n){
  int *num = malloc(sizeof(int)*n);
  return num;
}
int main(void){
  int *num;
  num = f(10);
  free(num);
  return 0;
}
E void f(int n){
  char *m = malloc(10);
  char *n = malloc(10);
  free(m);
  m = n;
  free(m);
  free(n);
}
O trecho que apresenta falhas é o E.
Ou seja, o ponteiro m é liberado antes de ser atribuído a n.
Portanto, m = n está dando a n a variável m. Isso faz com que m agora aponte para a mesma posição de memória que n. Assim, como ambas as variáveis estão apontando para a mesma região de memória após m = n, acaba que está liberando a mesma região duas vezes, o que pode causar um comportamento indefinido no código.>
 --------------------------------------------------------------------------------------------------------------------------------
  Questão 22:
  <#include <stdio.h>
int main(void){
  int a, b;
  int x, y, z;
  scanf("%d %d", &a, &b);
  x = a; y = b; z = a + b;
  while (a) {
  x = x | b;
  y = y ^ a;
  z = z & (a+b);
  a = a >> 1;
  b = b << 1;
  }
  printf ("%d %d %d\n", x, y, z);
  return 0;
}
Caso o usuário entre com os números 10 e 1, o programa irá resolver o seguinte:
Na primeira iteração do loop, a será deslocado uma posição para a direita (a >> 1) e b será deslocado uma posição para a esquerda (b << 1). Isso acontece até a se tornar zero.
Durante as iterações, x é atualizado usando o operador de "OU" bit a bit (x | b), y é atualizado usando o operador de "XOR" bit a bit (y ^ a), e z é atualizado usando o operador de "E" bit a bit (z & (a+b)).
Após o término do loop, o programa imprime os valores de x, y e z.
Calculando a = 10 e b = 1:
Na primeira iteração do loop, a se torna 5 e b se torna 2.
Na segunda iteração, a se torna 2 e b se torna 4.
Na terceira iteração, a se torna 1 e b se torna 8.
Na quarta iteração, a se torna 0 e b se torna 16.
Após a quarta iteração, o loop termina.
Calculando os valores de x, y e z:
x é atualizado em cada iteração do loop com x | b. Isso significa que x sempre conterá um "OU" bit a bit dos valores de a e b a cada iteração. Portanto, o valor final de x será 10 | 1 = 11.
y é atualizado em cada iteração do loop com y ^ a. Isso significa que y sempre conterá um "XOR" bit a bit dos valores de a e b a cada iteração. Portanto, o valor final de y será 10 ^ 1 = 11.
z é atualizado em cada iteração do loop com z & (a+b). Isso significa que z sempre conterá um "E" bit a bit dos valores de a e b a cada iteração. Portanto, o valor final de z será 11 & (10+1) = 11.
Portanto, a saída do programa será: 11 11 11.>
 ----------------------------------------------------------------------------------------------------------------------------------
 Questão 23:
 <#include <stdio.h>
#define TAM 10
int funcaol(int vetor[], int v){
  int i;
  for (i = 0; i < TAM; i++){
  if (vetor[i] == v)
  return i;
  }
  return -1;
}
int funcao2(int vetor[], int v, int i, int f){
  int m = (i + f) / 2;
  if (v == vetor[m])
  return m;
  if (i >= f)
  return -1;
  if (v > vetor[m])
  return funcao2(vetor, v, m+l, f);
  else
  return funcao2(vetor, v, i, m-1);
}
  int main(){
  int vetor[TAM] = {1, 3, 5, 7, 9, 11, 13, 15, 17, 19};
  printf("%d - %d", funcao1(vetor, 15), funcao2(vetor, 15, 0, TAM-1));
  return 0;
}
De acordo com o código acima, a resposta correta é a opção VI. I e II, apenas. Pois, a afirmação I está correta porque o resultado da impressão é de fato "7 - 7". 
A afirmação II está também correta, pois no pior caso, a funcao1 é mais rápida do que a funcao2. 
A afirmação III está incorreta, pois a funcao2 implementa uma estratégia que é recursiva, não iterativa.>
 ----------------------------------------------------------------------------------------------------------------------------
 Questão 24:
 <>
 ----------------------------------------------------------------------------------------------------------------------------------
 Questão 25:
 <>
