# Linguagens e Compiladores

### Sumário:

- [Linguagens de programação](#linguagens-de-programação)
- [Alto e baixo nível](#alto-e-baixo-nível)
- [Linguagem compilada e interpretada](#linguagem-compilada-e-interpretada)
- [Compilada e interpretada]()
- [Tipagem de dados]()

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

