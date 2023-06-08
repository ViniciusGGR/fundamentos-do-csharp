# Linguagem de Programação com C#

### Sumário:

- [Notas importantes](#notas-importantes)
- [Escopo de um programa](#escopo-de-um-programa)
    - [Fluxo de execução de uma aplicação ``.NET``](#fluxo-de-execução-de-uma-aplicação-net)
- [Namespaces](#namespaces)
- [Using]()
- [Variáveis]()
- [Constantes]()
- [Palavras reservadas]()
- [Comentários]()
- [Tipos primitivos]()
- [System]()
- [Byte]()
- [Números inteiros]()
- [Números reais]()
- [Boolean]()
- [Char]()
- [String]()
- [Var]()
- [Object]()
- [Nullabel Types]()
- [Alias]()
- [Valores padrões]()
- [Conversão implícita]()
- [Conversão explícita]()
- [Parse]()
- [Convert]()
- [Convertendo tipos]()
- [Operadores aritméticos]()
- [Operadores de atribuição]()
- [Operadores de comparação]()
- [Utilizando operadores]()
- [Operadores lógicos]()
- [Operador condicional: IF]()
- [Utilizando IF]()
- [Estrutura condicional: Switch]()
- [Laços de repetição: For]()
- [Laços de repetição: While]()
- [Laços de repetição: Do/While]()
- [Métodos e funções]()
- [Métodos e funções: Prática]()
- [Value Types e Reference Types]()
- [Value Types e Reference Types: Prática]()
- [Structs]()
- [Structs: Prática]()
- [Enums]()

---

## Notas importantes

Definições:

- Não utilizar _espaços_ nem _caracteres especiais_ na criação do programa.
    - Bons: ``MeuApp``, ``Pedidos``, ``MinhaApp``...
    - Ruins: ``"Meu App"``, ``$APP``, ``App #Teste``...
    > Sempre _comece_ o ``nome do projeto`` com **letra maiúscula**.
- Tente utilizar _caminhos curtos_ e sem **caracteres especiais**.
    - Bons: ``C:\dev``, ``C:\apps``...
    - Ruins: ``C:\Caminho Com Espaços e Caracteres Especiais\Meu App``...
- Evite _caminhos/diretórios_ de **rede**.
    > **Se possível**, utilize o ``C:\``.
- O **C#** é _Code Sensitive_.
    - Isto significa que ele _diferencia_ **maiúsculas** de **minúsculas**.
    - ``Teste`` é diferente de ``teste``.

---

## Escopo de um programa

**Escopo de um programa** é tudo que um _programa/aplicação_ **tem/precisa** para ser _executado_.

Definições:

- Importações.
    - Exemplo: _Importação_ do _módulo_ para **escrita de arquivos em disco**, do _módulo_ para **acesso a um banco de dados (BD)**.
    > **Todas as importações** ficam no _começo do arquivo/programa_.

    Exemplo de **importação** que sempre será definida pelo ``using``:
    ```
    using System;
    ```
- Namespace
    - Separações/Divisões lógicas dentro da aplicação, nomes (palavras reservadas) dentro do arquivo.
    > A **divisão física** é feita através de **arquivos** no (Windpws, Linux e/ou macOS).

    ```
    namespace MeuApp
    {

    }
    ```
    - É possível ter arquivos em _pastas diferentes_, mas com o **mesmo nome** e isso pode/vai ocasionar _conflitos_ nesses arquivos.
- Classe
    - É o programa em "si", pois tudo que será **executado** do _programa/aplicação_ está **dentro** de uma ``class``, normalmente essa **classe** tem o nome de ``Program``.
    ```
    class Program
    {

    }
    ```
- Método Principal/``Main``
    - O **método** ``Main`` "sempre" será _executado_ em primeiro lugar.
    ```
    static void Main(string[] args)
    {
        Console.WriteLine("Hello World!");
    }
    ```

O arquivo ``Program.cs`` é o "arquivo de entrada" de qualquer aplicação ``.NET``.

### Fluxo de execução de uma aplicação ``.NET``

Ao executar uma _aplicação_, um arquivo ``Program.cs`` é "procurado", depois é lido a ``class Program`` dentro desse arquivo e depois lê o método ``Main`` dentro dessa **class**.

---

## Namespaces

