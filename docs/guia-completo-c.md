# 📚 Algoritmos e Programação A - Guia Completo

Bem-vindo ao guia completo de **Algoritmos e Programação A**! Este material contém todo o conteúdo organizado de forma didática para dominar a linguagem C.

## 📑 Índice

1. [📌 Introdução à Linguagem C](#-introdução-à-linguagem-c)
2. [📋 Estrutura Básica de um Programa](#-estrutura-básica-de-um-programa)
3. [🔣 Tipos de Dados](#-tipos-de-dados)
4. [➕ Operadores](#-operadores)
5. [🖥️ Entrada e Saída de Dados](#️-entrada-e-saída-de-dados)
6. [🔄 Estruturas de Repetição](#-estruturas-de-repetição)
7. [📦 Vetores (Arrays)](#-vetores-arrays)
8. [🔢 Matrizes](#-matrizes)
9. [🔤 Strings](#-strings)
10. [🧮 Conceitos Avançados](#-conceitos-avançados)
11. [🛠️ Exemplos Práticos](#️-exemplos-práticos)
12. [📋 Referência Rápida](#-referência-rápida)

---

## 📌 Introdução à Linguagem C

### O que é a Linguagem C?

A linguagem C é uma linguagem de programação **compilada**, criada por Dennis Ritchie em 1972. É amplamente usada para desenvolvimento de sistemas operacionais, aplicações embarcadas e programas de alto desempenho.

### Diretiva `#include <stdio.h>`

- **O que é?** Importa a biblioteca padrão de entrada e saída (`Standard Input Output`)
- **Para que serve?** Permite usar funções como:
  - `printf()` - para imprimir dados na tela
  - `scanf()` - para ler dados do usuário
  - `getchar()` - para ler um caractere
  - `puts()` - para imprimir strings

### Outras Bibliotecas Importantes:

```c
#include <string.h>  // Funções de manipulação de strings
#include <math.h>    // Funções matemáticas
#include <stdlib.h>  // Funções de sistema (malloc, free, etc.)
```

---

## 📋 Estrutura Básica de um Programa

Todo programa em C segue esta estrutura:

```c
#include <stdio.h> // Biblioteca para entrada e saída

int main() {       // Função principal do programa
    printf("Olá, mundo!\n"); // Mostra mensagem na tela
    return 0;      // Indica que terminou com sucesso
}
```

**Explicando:**
- `int main()`: Função obrigatória, onde o programa começa a executar
- `return 0`: Diz ao sistema operacional que o programa terminou corretamente

---

## 🔣 Tipos de Dados

Os tipos de dados definem que **tipo de informação** uma variável pode armazenar.

### Tipos Básicos

| Tipo | Tamanho | Faixa de Valores | Descrição |
|------|---------|------------------|-----------|
| `int` | 4 bytes | -2,147,483,648 a 2,147,483,647 | Números inteiros |
| `float` | 4 bytes | 6-7 dígitos decimais | Números reais (precisão simples) |
| `double` | 8 bytes | 15-16 dígitos decimais | Números reais (precisão dupla) |
| `char` | 1 byte | -128 a 127 ou 0 a 255 | Um caractere |

### Declaração de Variáveis

```c
// Sintaxe: tipo nome_da_variavel = valor;

int idade = 20;
float altura = 1.75;
double peso = 70.5;
char inicial = 'V';
```

### Modificadores de Tipo

```c
short int num1 = 100;        // 2 bytes
long int num2 = 1000000;     // 8 bytes
unsigned int num3 = 500;     // apenas positivos

signed char letra = 'A';     // -128 a 127
unsigned char codigo = 255;  // 0 a 255
```

### Constantes

```c
const int MAXIMO = 100;      // Valor não pode ser alterado
#define PI 3.14159           // Macro constante
```

---

## ➕ Operadores

### 🔢 Operadores Aritméticos

Usados para fazer operações matemáticas.

| Operador | Nome | Função | Exemplo | Resultado |
|----------|------|--------|---------|-----------|
| `+` | Soma | Adiciona dois valores | `5 + 3` | `8` |
| `-` | Subtração | Subtrai valores | `5 - 2` | `3` |
| `*` | Multiplicação | Multiplica valores | `4 * 2` | `8` |
| `/` | Divisão | Divide valores | `10 / 2` | `5` |
| `%` | Módulo | Resto da divisão | `7 % 3` | `1` |

#### Operador Módulo (`%`) - Explicação Detalhada

O operador módulo retorna o **resto da divisão inteira**.

```c
7 % 3 = 1  // 7 ÷ 3 = 2 com resto 1
10 % 4 = 2 // 10 ÷ 4 = 2 com resto 2
8 % 2 = 0  // 8 ÷ 2 = 4 com resto 0
```

**Usos Práticos:**

```c
// Verificar se um número é par ou ímpar:
int numero = 7;
if (numero % 2 == 0) {
    printf("Par");
} else {
    printf("Ímpar");
}

// Verificar múltiplos:
if (numero % 5 == 0) {
    printf("É múltiplo de 5");
}
```

#### Operadores de Incremento e Decremento

| Operador | Nome | Função | Exemplo |
|----------|------|--------|---------|
| `++` | Incremento | Adiciona 1 | `i++` ou `++i` |
| `--` | Decremento | Subtrai 1 | `i--` ou `--i` |

#### Operadores de Atribuição Composta

| Operador | Equivale a | Exemplo |
|----------|------------|---------|
| `+=` | `a = a + b` | `x += 5` |
| `-=` | `a = a - b` | `x -= 3` |
| `*=` | `a = a * b` | `x *= 2` |
| `/=` | `a = a / b` | `x /= 4` |
| `%=` | `a = a % b` | `x %= 3` |

### 📏 Operadores Relacionais (Comparação)

Usados para **comparar valores** e retornam verdadeiro (1) ou falso (0).

| Operador | Nome | Função | Exemplo | Resultado |
|----------|------|--------|---------|-----------|
| `==` | Igual a | Verifica igualdade | `5 == 5` | `1` (true) |
| `!=` | Diferente de | Verifica diferença | `5 != 3` | `1` (true) |
| `<` | Menor que | Primeiro < segundo | `3 < 4` | `1` (true) |
| `>` | Maior que | Primeiro > segundo | `4 > 6` | `0` (false) |
| `<=` | Menor ou igual | Primeiro ≤ segundo | `5 <= 5` | `1` (true) |
| `>=` | Maior ou igual | Primeiro ≥ segundo | `6 >= 3` | `1` (true) |

⚠️ **Cuidado**: Não confunda `=` (atribuição) com `==` (comparação)!

### ⚙️ Operadores Lógicos

Usados para **combinar expressões lógicas** (verdadeiras ou falsas).

| Operador | Nome | Função | Quando é verdadeiro |
|----------|------|--------|-------------------|
| `&&` | E (AND) | Ambas condições verdadeiras | **Ambas** precisam ser verdade |
| `\|\|` | OU (OR) | Pelo menos uma verdadeira | **Pelo menos uma** precisa ser verdade |
| `!` | NÃO (NOT) | Inverte o valor lógico | Inverte verdadeiro ↔ falso |

#### Tabela Verdade

**Operador `&&` (E):**
| A | B | A && B |
|---|---|--------|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**Operador `||` (OU):**
| A | B | A \|\| B |
|---|---|----------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

---

## 🖥️ Entrada e Saída de Dados

### Função `printf()` - Saída de Dados

A função `printf()` é usada para **exibir informações** na tela.

```c
printf("formato", variáveis);
```

#### Especificadores de Formato:

| Tipo | Formato | Exemplo |
|------|---------|---------|
| `int` | `%d` | `printf("%d", 42);` |
| `float`/`double` | `%f` | `printf("%.2f", 3.14);` |
| `char` | `%c` | `printf("%c", 'A');` |
| `string` | `%s` | `printf("%s", "Olá");` |

### Função `scanf()` - Entrada de Dados

A função `scanf()` é usada para **ler dados** digitados pelo usuário.

```c
scanf("formato", &variável);
```

⚠️ **IMPORTANTE**: Use `&` antes do nome da variável (exceto para strings).

### Exemplo Completo:

```c
#include <stdio.h>

int main() {
    int idade;
    float altura;
    char nome[50];
    
    printf("=== CADASTRO PESSOAL ===\n");
    
    printf("Nome: ");
    fgets(nome, 50, stdin);
    
    printf("Idade: ");
    scanf("%d", &idade);
    
    printf("Altura (m): ");
    scanf("%f", &altura);
    
    printf("\n=== DADOS INFORMADOS ===\n");
    printf("Nome: %s", nome);
    printf("Idade: %d anos\n", idade);
    printf("Altura: %.2f metros\n", altura);
    
    return 0;
}
```

---

## 🔄 Estruturas de Repetição

### 🔂 Laço FOR

O laço `for` é usado quando você **sabe exatamente quantas vezes** quer repetir uma operação.

```c
for (inicialização; condição; incremento) {
    // código a ser repetido
}
```

**Exemplo Básico:**
```c
for (int i = 1; i <= 3; i++) {
    printf("Repetição %d\n", i);
}
```

**Passo a Passo do Exemplo:**

| Passo | Ação | Valor de `i` | Condição `i <= 3` | Execução | Saída |
|-------|------|--------------|-------------------|----------|-------|
| 1 | Inicialização | `i = 1` | - | - | - |
| 2 | Verificação | 1 | Verdadeira ✅ | Sim | `Repetição 1` |
| 3 | Incremento | `i = 2` | - | - | - |
| 4 | Verificação | 2 | Verdadeira ✅ | Sim | `Repetição 2` |
| 5 | Incremento | `i = 3` | - | - | - |
| 6 | Verificação | 3 | Verdadeira ✅ | Sim | `Repetição 3` |
| 7 | Incremento | `i = 4` | - | - | - |
| 8 | Verificação | 4 | Falsa ❌ | **PARA** | - |

**Variações do FOR:**

```c
// Contagem decrescente:
for (int i = 5; i >= 1; i--) {
    printf("%d\n", i);
}

// Incremento de 2 em 2:
for (int i = 0; i <= 10; i += 2) {
    printf("%d ", i);
}

// Múltiplas variáveis:
for (int i = 0, j = 10; i <= j; i++, j--) {
    printf("i=%d, j=%d\n", i, j);
}
```

### 🌀 Laço WHILE

O laço `while` executa um bloco de código **enquanto uma condição for verdadeira**.

```c
while (condição) {
    // código a ser repetido
}
```

**Como Funciona:**
1. **Verifica a condição** ANTES de executar
2. Se for **verdadeira**, executa o código
3. **Retorna para verificar** a condição novamente
4. **Para** quando a condição for falsa

⚠️ **Importante**: Se a condição for falsa desde o início, **o código nunca executa**.

**Exemplo:**
```c
int i = 1;
while (i <= 3) {
    printf("Repetição %d\n", i);
    i++;  // IMPORTANTE: incrementar para não ficar infinito!
}
```

### 🔁 Laço DO-WHILE

O laço `do-while` **executa o código pelo menos uma vez** e depois verifica a condição.

```c
do {
    // código a ser repetido
} while (condição);
```

⚠️ **Não esqueça do ponto e vírgula** após o `while`!

**Diferença Importante:**

```c
// while: Verifica ANTES de executar
int i = 10;
while (i <= 5) {
    printf("Nunca executa\n");  // Nunca roda
}

// do-while: Executa ANTES de verificar
int i = 10;
do {
    printf("Executa pelo menos uma vez\n");  // Roda uma vez
} while (i <= 5);
```

### Comandos Especiais nos Loops

#### `break` - Sair do Laço:
```c
for (int i = 1; i <= 10; i++) {
    if (i == 5) {
        break;  // para quando i = 5
    }
    printf("%d ", i);
}
// Saída: 1 2 3 4
```

#### `continue` - Pular Iteração:
```c
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;  // pula quando i = 3
    }
    printf("%d ", i);
}
// Saída: 1 2 4 5
```

---

## 📦 Vetores (Arrays)

Um vetor é uma **coleção de variáveis do mesmo tipo** armazenadas em sequência na memória.

### Declaração e Inicialização:

```c
// Declaração simples
int numeros[5];

// Declaração com inicialização
int numeros[5] = {10, 20, 30, 40, 50};

// Tamanho automático (baseado na inicialização)
int numeros[] = {1, 2, 3, 4, 5};
```

### Exemplo Prático:

```c
int numeros[5] = {10, 20, 30, 40, 50};

// Imprimir todos os elementos
for (int i = 0; i < 5; i++) {
    printf("numeros[%d] = %d\n", i, numeros[i]);
}

// Somar todos os elementos
int soma = 0;
for (int i = 0; i < 5; i++) {
    soma += numeros[i];
}
printf("Soma total: %d\n", soma);
```

📌 **Lembrete**: a contagem do índice **começa em 0**.

---

## 🔢 Matrizes

Uma matriz é como uma **tabela** (linhas x colunas).

### Declaração:

```c
// Matriz 2x3 (2 linhas, 3 colunas)
int matriz[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};
```

### Exemplo Prático:

```c
int matriz[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};

for (int i = 0; i < 2; i++) {        // linhas
    for (int j = 0; j < 3; j++) {    // colunas
        printf("%d ", matriz[i][j]);
    }
    printf("\n");
}
```

**Saída:**
```
1 2 3
4 5 6
```

---

## 🔤 Strings

Em C, uma string é um **vetor de `char`** finalizado com `'\0'` (caractere nulo).

### Declaração:

```c
char nome[20] = "Vinicius";
char nome[] = "Vinicius";           // Tamanho automático
char nome[20];                      // Declaração vazia
```

### O Caractere `\0`

- **Para que serve?** Para o compilador **saber onde a string termina**
- **Importante**: Todas as strings **terminam com o caractere nulo `\0`**

```c
// PROBLEMÁTICO ❌
char nome[6] = {'V','i','n','i','c','i'}; // sem \0
printf("%s", nome); // COMPORTAMENTO INDETERMINADO

// CORRETO ✅
char nome[7] = {'V','i','n','i','c','i','\0'}; // com \0
printf("%s", nome); // Saída: Vinici
```

### Lendo Strings:

```c
char nome[20];

// Método 1: scanf() - lê até o primeiro espaço
printf("Digite seu nome: ");
scanf("%s", nome);  // SEM & para strings!

// Método 2: fgets() - mais seguro, lê linha completa
char frase[100];
printf("Digite uma frase: ");
fgets(frase, 100, stdin);
```

### Principais Funções de String (`#include <string.h>`):

| Função | O que faz | Exemplo | Resultado |
|--------|-----------|---------|-----------|
| `strlen(str)` | Retorna o tamanho da string | `strlen("Oi")` | `2` |
| `strcpy(dest, orig)` | Copia `orig` para `dest` | `strcpy(nome,"João");` | `nome = "João"` |
| `strcat(dest, orig)` | Concatena `orig` no final de `dest` | `strcat("Oi ","Mundo")` | `"Oi Mundo"` |
| `strcmp(str1,str2)` | Compara duas strings | `strcmp("oi","oi")` | `0` (iguais) |
| `strchr(str,c)` | Procura caractere na string | `strchr("banana",'n')` | Ponteiro para primeira ocorrência |
| `strstr(str,sub)` | Procura substring | `strstr("algoritmo","rit")` | Ponteiro para "ritmo" |
| `puts(str)` | Imprime string com quebra de linha | `puts("Olá")` | `Olá\n` |
| `gets(str)` | Lê string do teclado até ENTER | `gets(nome)` | ⚠️ **Não seguro, pode causar overflow** |
| `fgets(str,n,stdin)` | Lê até n-1 caracteres com segurança | `fgets(nome,50,stdin)` | Seguro, mas inclui `\n` |
| `strtok(str, delim)` | Divide string em tokens | `strtok("Olá Mundo"," ")` | Retorna `"Olá"` (primeiro token) |

### Exemplos Práticos das Funções:

#### `puts()` vs `printf()`:
```c
puts("Olá mundo");        // Adiciona \n automaticamente
printf("Olá mundo\n");    // Precisa adicionar \n manualmente
```

#### `gets()` vs `fgets()` (Segurança):
```c
char nome[20];

// PERIGOSO ❌ - pode causar overflow
gets(nome);

// SEGURO ✅ - limita o tamanho
fgets(nome, 20, stdin);
```

#### `strtok()` - Dividir strings:
```c
char frase[] = "João Silva 25";
char *token;

token = strtok(frase, " ");  // Primeiro token: "João"
while (token != NULL) {
    printf("%s\n", token);
    token = strtok(NULL, " ");  // Próximos tokens
}
// Saída: João, Silva, 25
```

#### Remover `\n` do `fgets()`:
```c
char nome[50];
fgets(nome, 50, stdin);

// Remove o \n que fgets() inclui
nome[strcspn(nome, "\n")] = '\0';
// ou usando strtok:
strtok(nome, "\n");
```

---

## 🧮 Conceitos Avançados

### 🔢 Variável Contadora

Uma variável que **aumenta ou diminui de forma controlada** durante a execução do programa. Usada para contar quantas vezes algo acontece.

```c
int contador = 0;

for (int i = 1; i <= 5; i++) {
    contador++; // soma +1 a cada volta
}
printf("O laço rodou %d vezes", contador);
// Saída: O laço rodou 5 vezes
```

### ➕ Variável Acumuladora

Serve para **somar valores** ao longo do programa.

```c
int soma = 0; // acumulador inicializado com 0

for (int i = 1; i <= 5; i++) {
    soma += i; // mesma coisa que soma = soma + i
}
printf("Soma = %d", soma);
// Saída: Soma = 15 (1+2+3+4+5)
```

### 🚩 Flag (Bandeira)

Uma **variável lógica** usada para indicar se uma condição aconteceu. Normalmente é um `int` (0 = falso, 1 = verdadeiro).

```c
int achou = 0; // flag inicializada como falso
int vetor[5] = {1, 3, 5, 7, 9};

for (int i = 0; i < 5; i++) {
    if (vetor[i] == 7) {
        achou = 1; // liga a flag
        break;
    }
}

if (achou == 1) {
    printf("Número encontrado!");
} else {
    printf("Número não encontrado!");
}
```

---

## 🛠️ Exemplos Práticos

### 1. Calculadora Simples

```c
#include <stdio.h>

int main() {
    float num1, num2;
    char operacao;
    
    printf("Digite dois números: ");
    scanf("%f %f", &num1, &num2);
    
    printf("Digite a operação (+, -, *, /): ");
    scanf(" %c", &operacao);
    
    switch(operacao) {
        case '+':
            printf("%.2f + %.2f = %.2f\n", num1, num2, num1 + num2);
            break;
        case '-':
            printf("%.2f - %.2f = %.2f\n", num1, num2, num1 - num2);
            break;
        case '*':
            printf("%.2f * %.2f = %.2f\n", num1, num2, num1 * num2);
            break;
        case '/':
            if (num2 != 0) {
                printf("%.2f / %.2f = %.2f\n", num1, num2, num1 / num2);
            } else {
                printf("Erro: Divisão por zero!\n");
            }
            break;
        default:
            printf("Operação inválida!\n");
    }
    
    return 0;
}
```

### 2. Tabuada

```c
int numero;
printf("Digite um número: ");
scanf("%d", &numero);

printf("=== TABUADA DO %d ===\n", numero);
for (int i = 1; i <= 10; i++) {
    printf("%d x %d = %d\n", numero, i, numero * i);
}
```

### 3. Validação de Entrada

```c
int numero;
printf("Digite um número positivo: ");
scanf("%d", &numero);

while (numero <= 0) {
    printf("❌ Número inválido! Digite novamente: ");
    scanf("%d", &numero);
}

printf("✅ Número válido: %d\n", numero);
```

### 4. Menu Interativo

```c
int opcao = 0;

while (opcao != 4) {
    printf("\n=== MENU ===\n");
    printf("1. Cadastrar\n");
    printf("2. Consultar\n");
    printf("3. Relatório\n");
    printf("4. Sair\n");
    printf("Escolha uma opção: ");
    scanf("%d", &opcao);
    
    switch (opcao) {
        case 1:
            printf("Cadastro realizado!\n");
            break;
        case 2:
            printf("Consulta realizada!\n");
            break;
        case 3:
            printf("Relatório gerado!\n");
            break;
        case 4:
            printf("Saindo...\n");
            break;
        default:
            printf("Opção inválida!\n");
    }
}
```

### 5. Busca em Vetor

```c
int vetor[5] = {10, 20, 30, 40, 50};
int procurado, posicao = -1;

printf("Digite o número a procurar: ");
scanf("%d", &procurado);

for (int i = 0; i < 5; i++) {
    if (vetor[i] == procurado) {
        posicao = i;
        break;
    }
}

if (posicao != -1) {
    printf("Número encontrado na posição %d\n", posicao);
} else {
    printf("Número não encontrado\n");
}
```

### 6. Maior e Menor Valor em Vetor

```c
int numeros[5] = {15, 3, 8, 25, 12};
int maior = numeros[0];
int menor = numeros[0];

for (int i = 1; i < 5; i++) {
    if (numeros[i] > maior) {
        maior = numeros[i];
    }
    if (numeros[i] < menor) {
        menor = numeros[i];
    }
}

printf("Maior valor: %d\n", maior);
printf("Menor valor: %d\n", menor);
```

### 7. Contar Vogais em uma String

```c
#include <stdio.h>
#include <string.h>

int main() {
    char texto[100];
    int contador = 0;
    
    printf("Digite uma frase: ");
    fgets(texto, 100, stdin);
    
    for (int i = 0; i < strlen(texto); i++) {
        char c = texto[i];
        if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' ||
            c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U') {
            contador++;
        }
    }
    
    printf("Quantidade de vogais: %d\n", contador);
    return 0;
}
```

---

## 📋 Referência Rápida

### Caracteres Especiais

| Caractere | Função |
|-----------|--------|
| `\n` | Nova linha |
| `\t` | Tabulação |
| `\"` | Aspas duplas |
| `\'` | Aspas simples |
| `\\` | Barra invertida |

### Precedência dos Operadores

**Ordem de precedência** (do maior para o menor):

1. `()` - Parênteses
2. `!`, `++`, `--` - Operadores unários
3. `*`, `/`, `%` - Multiplicação, divisão, módulo
4. `+`, `-` - Soma, subtração  
5. `<`, `<=`, `>`, `>=` - Operadores relacionais
6. `==`, `!=` - Igualdade e diferença
7. `&&` - E lógico
8. `||` - OU lógico

### Quando Usar Cada Tipo de Loop

| Loop | Quando Usar | Exemplo |
|------|-------------|---------|
| `for` | Souber exatamente quantas repetições | Percorrer arrays, contadores fixos |
| `while` | Não souber quantas repetições | Validação de entrada, condições específicas |
| `do-while` | Executar pelo menos uma vez | Menus, validações que precisam rodar ao menos uma vez |

### Dicas de Compilação


```bash
# Compilar um programa
gcc programa.c -o programa

# Executar
./programa

# Compilar com warnings
gcc -Wall programa.c -o programa

# Incluir biblioteca math.h
gcc programa.c -lm -o programa
```

---

## 🎯 Objetivos de Aprendizado

Ao final deste guia, você será capaz de:

- ✅ Entender a estrutura básica de um programa em C
- ✅ Trabalhar com diferentes tipos de dados
- ✅ Usar operadores aritméticos, relacionais e lógicos
- ✅ Implementar estruturas de repetição eficientemente
- ✅ Manipular vetores e matrizes
- ✅ Processar strings e usar funções de manipulação
- ✅ Usar contadores, acumuladores e flags
- ✅ Resolver problemas algorítmicos básicos

## 💡 Dicas de Boas Práticas

1. **Sempre inicialize** suas variáveis
2. **Use nomes descritivos** para variáveis e funções
3. **Comente seu código** para facilitar a manutenção
4. **Teste sempre** os casos limite (zero, números negativos, etc.)
5. **Cuidado com loops infinitos** - sempre tenha uma forma de sair
6. **Use `fgets()` ao invés de `gets()`** para strings
7. **Verifique divisão por zero** antes de dividir
8. **Use parênteses** para deixar expressões mais claras

## 📚 Recursos Adicionais

- [Documentação Oficial do C](https://en.cppreference.com/w/c)
- [Compilador Online](https://www.onlinegdb.com/online_c_compiler)
- [Exercícios Online](https://www.hackerrank.com/domains/c)

---

**💡 OBS**: Guia de estudo da linguagem C, elaborado por Vinicius Arruda. Conteúdo organizado para fins de aprendizado, referência e prática acadêmica."

*Guia completo atualizado em 2025*