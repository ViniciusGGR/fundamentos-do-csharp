# Linguagem de Programação com C#

### Sumário:

- [Notas importantes](#notas-importantes)
- [Escopo de um programa](#escopo-de-um-programa)
    - [Fluxo de execução de uma aplicação ``.NET``](#fluxo-de-execução-de-uma-aplicação-net)
- [Namespaces](#namespaces)
- [Using](#using)
- [Variáveis](#variáveis)
    - [Padronização de Nomes](#padronização-de-nomes)
- [Constantes](#constantes)
- [Palavras reservadas](#palavras-reservadas)
- [Comentários](#comentários)
- [Tipos primitivos](#tipos-primitivos)
- [System](#system)
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

Definições:

- Os ``namespaces`` são as **divisões lógicas**.
    - Os ``namespaces`` **não permitem** a criação de _duas classes_ com o mesmo nome em um ``namespace``.
        - Normalmente o ``namespace`` "acompanha" o nome da _pasta/arquivo_ no qual ele está.
    - O ideal é ter _apenas_ um ``namespace`` e uma ``class`` por **arquivo**.
        - Caso precise ter duas **classes** com "mesmo nome" em _pastas diferentes_, basta colocar um (``.OtherName``) depois do nome do ``namespace``.
    - O "escopo" de um ``namespace`` é _definido_ entre **CHAVES** ``{}``.
        - **Classes** e **Métodos** também.
    - Um ``namespace`` pode ser _reutilizado_.
        - Pode estar presente em **diversos arquivos**.
        - Um mesmo ``namespace`` pode ser reutilizado em outros arquivos, mas esses novos arquivos **não podem ter** uma **classe** com mesmo nome de outra **classe** já presente em outro arquivo.
            - Dois ``namespaces`` iguais é permitido em arquivos diferentes, mas com nomes de **classes** diferentes.

> Os ``namespaces`` são as **divisões lógicas** e as "_pastas/diretórios_" são as **divisões físicas**.

- É possível criar quantos ``namespaces`` quiser.
- Não devem conter **espaços** ou **caracteres especiais**.
- Toda palavra no ``namespace`` começa com **maiúsculo**.
- É possível ter um ``namespace`` _dentro de outro_ (pseudo-namespace) usando (``.``).
- A **importação** é feita pelos ``namespaces``.
    - Caso queira **importar** um ``namespace`` de outra pasta para o arquivo atual, por exemplo o ``namespace`` (MeuApp.Teste), basta **importar** esse ``namespace`` em outro arquivo com o _comando_: ``using MeuApp.Teste;``

- Durante a execução, todos os arquivos **C#** serão _unificados_.
    - O resultado será uma ``DLL`` única.
- A **divisão física** se perderá.
- Sobrará apenas a **divisão lógica**, que são os ``namespaces``.

---

## Using

A _importação_ dos ``namespaces`` é feita através da "palavra reservada" **``using``**.

Definições:

- _Importações_ definem as **bibliotecas** que o programa irá utilizar.
    - Podendo ser **bibliotecas** _internas_ e _externas_.
- Por "padrão" no ``.NET`` só o _básico_ vem incluso.
- É preciso _importar_ o que se deseja para poder trabalhar.
- As _importações_ são feitas no **começo do programa** (é uma **boa prática**).
    - Para _importar_ se utiliza a "palavra reservada" ``using``.

- O ``using`` é útil para "organizar" o código em **pastas** e ``namespaces`` (isso é _fundamental_).
    - Em _aplicações grandes_, o volume de código é alto (quantidade de arquivos alta) e pode acabar "virando uma bagunça" se não bem organizado.
        - Número de pessoas trabalhando no mesmo projeto também é alto.
        > Entender bem esta _organização_ é fundamental.
- Use e abuse da **criação de arquivos** e ``namespaces``.

**Organização física** - São as _pastas_ e _arquivos_ do projeto.
**Organização lógica** - São os ``namespaces``. Então tudo o que se precisa é _importado_ através dos ``namespaces``, que são definidos pelos ``using`` no começo do arquivo.

---

## Variáveis

Definições:

- Uma **variável** é algo utilizado para _armazenar uma informação_.
- **variável** significa que o _valor (dessa informação armazenada)_ pode ser **alterado a qualquer momento**, ou seja, o _valor (informação armazenada)_ pode **variar**.
- Sempre que uma **variável** é "criada/instanciada", se diz que ela está sendo _inicializada_.
- Em **C#** pode se utilizar um **TIPO** ou _palavra reservada_ ``var`` para "criar/instanciar" uma **variável**.
    > Uma ``palavra reservada`` _não pode ser utilizada_ para **nomear uma variável**.
- No **C#** o _tipo_ (``var``, ``int``...) vem sempre antes do _nome da variável_.
    - O tipo ``var`` necessita de um **valor**, pois ele é um _tipo não definido_. Portanto, ao declarar uma **variável** do _TIPO_ ``var`` é necessário _informar um valor_ já na **criação da variável**.
    ```
    int idade;         // Correto - Inicia com 'ZERO'.
    int idade = 25;    // Correto - Inicia com '25'.
    var idade = 25;    // Correto - Inicia com '25'.
    var idade;         // Errado.
    ```
- É possível _informar um valor_ já na **criação da variável**, ou _posteriormente_.
    - Se **não informado** o _valor padrão_ será aplicado.

### Padronização de Nomes

Definições:

- Utilizar _nomes coesos_ em **variáveis**.
    - Isso facilita a leitura e entendimento do código por outras pessoas.
- Não deve-se utilizar _caracteres especiais_ ou _espaços_.
- Não deve começar com **números**.
- A _primeira letra_ do nome de uma **variável** é **SEMPRE** _minúscula_. Se a **variável** tiver _nome composto_ a _primeira letra da primeira palavra_ é **minúscula** e a _primeira letra das próximas palavras_ é **maiúscula**.

---

## Constantes

Definições:

- Uma **constante** também é utilizada para _armazenar uma informação_.
- As **constantes** ``NÃO PODEM`` ser _alteradas_.
    - Uma vez que uma **constante** é criada, _atribuir um valor_ se torna obrigatório.
    - Após essa _atribuição de valor_, uma **constante** ``NÃO PODERÁ`` ser _modificada_ novamente.
- Uma **constante** não funciona com a utilização de ``var``.
- Uma **constante** é mais _otimizada_ do que uma **variável**.
- São recomendadas para usos frequentes.

> As **constantes** são muito utilizadas para criar **regras** para o sistema, uma  _validação_ de qualquer tipo e definir uma **informação** que será _reutilizada_ em diversos lugares do sistema/aplicação, mas que essa **informação** _não pode variar (ser alterada)_.

- A definição de **constante** é dada pela _palavra reservada_ ``const`` antes do tipo.
- Caso não seja informado um valor, o **valor padrão** será atribuido.
    ```
    const int IDADE_MINIMA;         // Correto - Inicia com 'ZERO'.
    const int IDADE_MINIMA = 25;    // Correto - Inicia com '25'.
    const var IDADE_MINIMA = 25;    // Errado.
    const var IDADE_MINIMA;         // Errado.
    ```
- Utilize _nomes coesos_ em **constantes**.
- Não deve utilizar **caracteres especiais** ou **espaços**.
- Não deve começar com _números_.
- É comum ver **constantes** todas em _maiúsculas_, separadas por "``_``".
    - A ideia é "bater o olho no código" e saber que aquilo é uma **constante**.

> É uma **boa prática** _sempre inicializar variáveis/constantes_ no **C#**.

---

## Palavras reservadas

O **C#** possui _nomes reservados_, ou seja, significa que essas **palavras reservadas** não podem ser utilizadas na criação de _constantes/variáveis_.

Definições:

- **Palavras reservadas** também são chamadas de ``keywords``.
- São **palavras reservadas** de "uso exclusivo" do **C#**.
- Não podem ser utilizadas como _nomes de variáveis_ ou _constantes_.

> **Dica**: O ``VS Code`` avisa se um **nome/palavra** é **reservado** - (``keyword``).

- [Lista de ``Keywords`` no site da **Microsoft**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/)

---

## Comentários

Um **comentário** é um "_lembrete/descrição_" de algo que **não será executado pelo compilador**.

Definições:

- Em _diversos cenários_ é preciso "deixar" uma _mensagem_/**comentário**.
- Esta _mensagem_/**comentário** não deve ser _executada pelo programa_.
- É "comum" utilizar **comentários** em _linhas de código_ que não se deseja **executar**.
- É possível ter **comentários** de:
    - Uma linha - ``// Comment here``.
    - Múltiplas linhas - ``/* Comment here */``.
    - XML (Metadata). Esse modelo gera _informações adicionais_ sobre uma **classe** - ``/// Comment here``.

> **Atalho**: O _atalho_ para **comentar linha(s) no ``VS Code`` é**: ``Ctrl + k + c``. O _atalho_ para **descomentar linha(s) no ``VS Code`` é**: ``Ctrl + k + u``.

Evite **comentários** "bobos/tolos", que não são necessários para entender o código.

> **Comentários** também servem como forma de _documentar_ o seu código/projeto.

---

## Tipos primitivos

_Tipos de dados_ são os "tipos" que as **variáveis/constantes** podem ser no **C#**.

Definições:

- **Tipos Primitivos**, também conhecidos como ``built-in types``.
- São _tipos base_ que se tem no ``.NET``, cujo outros **tipos** (``Complexos``) irão derivar.
- _Definir_ o **tipo** correto do "dado" _otimiza a execução do programa_.
- Os **Tipos Primitivos**, também são chamados de **Tipos de Valor**.
- Os **Tipos Primitivos** _armazenam valor_ e não a referência para um item na memória.
- Os **Tipos Primitivos** são classificados em:
    - Tipos Simples (``Simple Types``).
    - Enumeradores (``Enums``).
    - Estruturas (``Structs``).
    - Tipos Nulos (``Nullable Types``).
- Cada **Tipo Primitivo** possui uma _capacidade_, isso que "difere" cada tipo de outro.
    - Caso esta _capacidade_ exceda, o programa gera um erro.
    - Esta _capacidade_ **pré-definida** ajuda na _otimização do programa_.
    - Por exemplo: O _tipo_ ``int``:
        - Vai de ``-2,147,483,648`` até ``2,147,483,647``. Qualquer valor _fora desse alcance_ **gerará um erro no programa**.

---

## System

