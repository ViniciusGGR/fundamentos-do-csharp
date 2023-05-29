# Linguagens e Compiladores

### Sumário:

- [Linguagens de programação](#linguagens-de-programação)
- [Alto e baixo nível](#alto-e-baixo-nível)
- [Linguagem compilada e interpretada](#linguagem-compilada-e-interpretada)
    - [Linguagens Compiladas](#linguagens-compiladas)
    - [Linguagens Interpretadas](#linguagens-interpretadas)
- [Compilada e interpretada](#compilada-e-interpretada)
    - [Linguagem Interpretada](#linguagem-interpretada)
    - [Linguagem Compilada](#linguagem-compilada)
- [Tipagem de dados](#tipagem-de-dados)

---

## Linguagens de programação

O que são **Linguagens de programação** (LP)?

- É a forma (_Comunicação_) como dizemos para o computador executar algo.
- Computadores "não falam" nossa língua, usam o formato **binário** (0 e 1) para fazer qualquer operação, executada dentro do _Processador_ (CPU), _GPU_, _memória_...
- Uma **Linguagem de programação** (LP) faz este _intermédio_:
    - O que escrevemos será "traduzido" para o formato **binário** (_linguagem de máquina_). 
    - Em resumo temos um **arquivo de texto** que:
        - Nós conseguimos ler.
        - Será "traduzido" para **binário** (0 e 1).
- Este processo de "tradução" é conhecido como ``compilação``.
- Existem várias **linguagens de programação** (LP):
    - Cada uma com seu **compilador**.
    - Cada **compilador** trabalha de uma forma.

> **Compilador**: _Agente_ que **executa a compilação**, que é a _transformação do texto_ que escrevemos para **binário** (0 e 1) - (_linguagem de máquina_).

---

## Alto e baixo nível

Definições:

- Ao "enviar" uma _instrução ao computador_ estamos falando em **nível de máquina**, próximo ao _CPU_.
- Estas **instruções** sempre serão no _formato_ **binário** (o e 1).
- Quanto mais detalhada a necessidade, mais **baixo nível**.
- As _linguagens mais modernas_ como **C#** e Java são consideradas de **alto nível** (mais próximas dos usuários/desenvolvedores).

Exemplos:

- Código em **Assembly** (``"Hello, World"``), uma _linguagem de baixo nível_:
    ```
            global _start

            section .text
    _start:    mov rax, 1
            mov rdl, 1
            rsi, message
            mov rdx, 13
            syscall
            mov rax, 60
            xor rdi, rdi
            syscall

            section .data
    message: db        "Hello, World", 10    
    ```

    Quanto mais **baixo nível**, mais controle a gente tem sobre o que se quer fazer, sobre _Processador_, _Memória_ e o computador em geral, só que mais difícil fica a leitura/escrita da linguagem.

- Código em **C#** (``"Hello, World"``), uma _linguagem de alto nível_:
    ```
    namespace ConsoleApp1
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Hello World");
            }
        }
    }
    ```

    O código em uma **linguagem de alto nível** é mais fácil de ler/entender, só que não se tem tanto controle sobre _Processador_, _Memória_ e o computador em geral quanto em uma **linguagem de baixo nível**.

    Uma **linguagem de alto nível** fornece um acesso a tudo o que se precisa em um _nível de hardware_ já pronto.

---

## Linguagem compilada e interpretada

### Linguagens Compiladas

Definições:

- Dada quando existe o _processo de **compilação**_ da mesma.
- Consiste em receber um _arquivo texto_ e "convertê-lo" para **binário** (0 e 1).
    - Normalmente otimizado para "_leitura de humanos_".

### Linguagens Interpretadas

Definições:

- Arquivos de texto "puro", e esses arquivos _não são convertidos_ para **binário**.
    - São "lidos" e **interpretados** por um "_intérprete_".
    - Feito em **tempo de execução** (tempo real).
- _JavaScript_ é **interpretado**.

> **Tempo de Execução**: É o que acontece durante a _execução do código_ pelo **computador** ou **interpretador**.

- No caso do _JavaScript_
    - O navegador é escrito em uma **linguagem de alto nível** (pode ser de **baixo nível** também).
    - Possui um **interpretador**.
    - "Lê" e _executa_ um arquivo de texto com _extensão JavaScript_.

    O navegador é o "intérprete" e em **tempo de execução** (tempo real) faz a interpretação do texto e executa o _JavaScript_.

---

## Compilada e interpretada

### Linguagem Interpretada

**Prós**:

- Não precisa ser **compilada**.
    - Não existe "tempo de **compilação**".
- _Correções_ mais fáceis de serem executadas.
- Mais simples de serem distribuidas (arquivos "estáticos").
- Não tem a necessidade de ser "traduzida" para uma _linguagem de máquina_.

**Contras**:

- Detecção de erros mais "difícil".
    - Erros "aparecerão" somente em "**tempo de execução**".
- Tamanho "final" da aplicação **maior**.
- Menor _otimização_ da execução.
- Múltiplos arquivos.

### Linguagem Compilada

**Prós**:

- Tempo de **compilação** - Tudo o que acontece enquanto o programa está sendo **compilado**.
    - Detecção mais rápida de erros.
- Tamanho "menor" das aplicações.
- Maior _otimização_ da execução.
- Apenas um arquivo final.

**Contras**:

- Precisa de um **compilador** (transforma a linguagem em uma _linguagem de máquina_ (baixo nível)).
- Pode ser mais "burocrática".

---

## Tipagem de dados

Definições:

- Também chamadas (conhecidas) de **fortemente tipadas**.
- _Obrigam_ a especificar o **tipo de dado** da informação que será armazenada em uma (``variável``).
- Menor liberdade, pois não é possível "criar" _qualquer tipo de informação_ dentro da aplicação.
- Maior **otimização**.

> **Tipo de Dado**: Um _tipo de dado_ define o "**formato**" dessa **informação**, onde definimos por exemplo que aquela **informação** é um _número_, uma _letra_, uma _cadeia de caracteres_ e assim por diante.

Uma ``variável`` é uma **informação** declarada que pode ser _alterada_ posteriormente.

Uma ``constante`` é uma **informação** que uma vez declarada, _nunca_ poderá ser _alterada_.

- **Exemplos em C#**:
    ```
    int age = 18;      // OK
    int age = 18.2;    // ERRO - (valor do tipo 'double')
    int age = "18";    // ERRO - (valor do tipo 'string')
    int age = 'a';     // ERRO - (valor do tipo 'char')
    ```

    A palavra-chave ``int`` define que essa ``variável`` recebe um valor **inteiro**, sem _casas decimais_, não tem _pontuação_.

    - Mesmo exemplo em _JavaScript_, uma **linguagem não tipada**:
        ```
        let idade = 18;      // OK
        let idade = 18.2;    // OK
        let idade = "18";    // OK
        let idade = 'a';     // OK
        ```

> **C#** é uma linguagem de **alto nível**, **compilada** e **fortemente tipada**.

Definições:

- A _tipagem de dados_ serve para definir **tipos** e _padronizar os dados/informações_.
    - Para nós e para o **processador/memória**.
- O ``let`` utiliza "sempre" o mesmo _tamanho de alocação_ (não tem **otimização**).
- **Tipando** temos uma _otimização_.

- No **C#** por exemplo:
    ```
    int => 32-bit
    float => 32 bit
    double => 64 bit
    decimal => 128 bit
    ```

---