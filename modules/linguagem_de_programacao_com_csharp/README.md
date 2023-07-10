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
- [Byte](#byte)
- [Números inteiros](#números-inteiros)
- [Números reais](#números-reais)
- [Boolean](#boolean)
- [Char](#char)
- [String](#string)
- [Var](#var)
- [Object](#object)
- [Nullabel Types](#nullabel-types)
    - [Void](#void)
    - [Null](#null)
- [Alias](#alias)
- [Valores padrões](#valores-padrões)
- [Conversão implícita](#conversão-implícita)
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

O ``System`` é o _tipo base_ do ``.NET``, é o _tipo_ que todos os outros "_tipos_" derivam.

Definições:

- No ``.NET`` tudo começa de um _tipo base/raiz_ chamado **``system``**.
- Todo e qualquer tipo, seja **built-in** ou **complexo** deriva do **``system``**.
- O **``system``** é a _base_ de todos os **objetos** no ``.NET``.
- Não é preciso se preocupar em usá-lo ou qualquer coisa similar.
- O uso do **``system``** já é _implícito_.

---

## Byte

Definições:

- O tipo ``byte`` (_tipo primitivo_ **built-jn type**) é utilizado para **representar** um "byte" de fato.
- Em diversos casos é preciso da _cadeia de bytes_ de um **arquivo** por exemplo.
    - _cadeia de bytes_ também chamado de **byte array**.
- Também existe o ``sbyte``, que permite _valores negativos_.

> **``Signed``** e **``Usigned``**: _Valores_ com sinal como "**-**" por exemplo, são chamados de **``signed``**.

- ``byte`` (8-bit).
    - O ``byte`` vai de **0** até **255**.
- ``sbyte`` (8-bit).
    - O ``sbyte`` vai de **-128** até **127**.

> **Nota**: O ``sbyte`` _permite valores negativos_, por isto no nome ``sbyte``, que significa **Signed Byte**.

```
byte meuByte = 127;
sbyte myByte = -56;
```

---

## Números inteiros

Definições:

- _Números inteiros_, ou seja, **sem pontuação**, podem ser definidos pelos _tipos_:
    - ``short``/``ushort`` - Utilizado para valores menores.
    - ``int``/``uint`` - Utilizado para valores intermediários.
    - ``long``/``ulong`` - Utilizado para valores maiores.
- Assim como o _signed_ nos **bytes** (``sbyte``), nos **_números_** por padrão são _permitidos valores negativos_.
    - Então o _unsigned_ é usado para **definir** que o mesmo _não pode receber valores negativos_ (``ushort``, ``uint``, ``ulong``).
- O _tipo_ ``int`` é o "mais comum" a ser encontrado.

- ``short`` - (16-bit).
    - aceita valores entre **-32,768** até **32,767**.
- ``ushort`` - (16-bit).
    - aceita valores entre **0** até **65.535**.
- ``int`` - (32-bit).
    - aceita valores entre **-2,147,483,648** até **2,147,483,647**.
- ``uint`` - (32-bit).
    - aceita valores entre **0** até **4,294,967,295**.
- ``long`` - (64-bit).
    - aceita valores entre **-9,223,372,036,854,775,808** até **9,223,372,036,854,775,807**.
- ``ulong`` - (64-bit).
    - aceita valores entre **0** até **18,446,744,073,709,551,615**.

---

## Números reais

Números reais, são _números_ que possuem (``.``). Também podem ser chamados de _números flutuates_ ou _números de ponto flutuante_.

Definições:

- São números que "exigem" uma _maior precisam_, ou seja, com **pontuação** (Números reais).
    - Tipo ``float`` (Possui a _notação_ **F/f**).
    - Tipo ``double``.
    - Tipo ``decimal`` (Possui a _notação_ **M/m**).
- Possuem _assimilação negativa e positiva_ por padrão, dispensando uso do **signed/unsigned** em seus _tipos_.

- Tipo ``float`` - (32-bit).
    - aceita valores entre **-3.402823e38** até **3.402823e38**.
- Tipo ``double`` - (64-bit).
    - aceita valores entre **-1.79769313486232e308** até **1.19769313486232e308**.
- Tipo ``decimal`` - (128-bit).
    - aceita valores entre (+ ou -) **1.0 x 10e-28** até **7.9 x 10e28**.

> O _tipo_ ``double`` é a _recomendação padrão_ a ser utilizada em programas **C#**.

---

## Boolean

Tipo ``Bool`` que vem do nome _Boolean_.

Definições:

- O _tipo_ **booleano**, armazena apenas ``true`` e ``false`` (**verdadeiro** ou **falso**).
- Definido pela _palavra reservada_ ``bool``.
- Tipo ``bool`` - (8-bit).
    - aceita os valores ``true`` ou ``false``.

---

## Char

Definições:

- O _tipo_ ``char`` é utilizado para armazenar **apenas um e somente um caractere** no formato _Unicode_.
- Definido pela _palavra reservada_ ``char``.
- A **atribuição** de um valor ``char`` é dada por **aspas simples** (``''``).
    - Com o tipo ``char`` _não pode ser utilizado **aspas duplas** (``""``) para atribuição de valores_.
- Tipo ``char`` - (16-bit).
    - Qualquer caractere no formato _Unicode_.

---

## String

Definições:

- O _tipo_ ``string``, armazena uma **cadeia de caracteres**.
- Pode-se pensar nele como um _lista de ``char``_.
- Definido pela _palavra reservada_ ``string``.
- A **atribuição** de um valor ``string`` é dada por **aspas duplas** (``""``).
    - Com o tipo ``string`` _não pode ser utilizado **aspas simples** (``""``) para atribuição de valores_.
- Tipo ``string`` - (Ocupação de memória é dinâmica).
    - Qualquer _cadeia de caracteres_.

---

## Var

Definições:

- O _tipo_ ``var``, "substitui" o _nome de um tipo_.
- O _tipo_ ``var`` **assume** o _tipo_ do **primeiro valor atribuído**.
- O uso do ``var`` é recomendado.
    > **Observação**: Deixe para usar o _tipo_ ``var`` quando já dominar os _tipos_.

```
var age = 25;    // Será do tipo 'int'.
var name = "Vinícius"    // Será do tipo 'string'.
```

> Definido o ``var`` uma vez, esse _tipo atribuído_ não poderá ser **alterado**.

---

## Object

Definições:

- O _tipo_ ``object`` é um **tipo genérico** que recebe qualquer "valor ou objeto".
- Caso não saiba o _tipo da informação_ ou ela seja de _vários tipos_ diferentes.
- Não possui **intelisense** (_Ajuda dos editores_) por ser um tipo desconhecido.
- Evite usar o _tipo_ ``object`` (por enquanto). 

```
object age = 25;    // Será do tipo 'object'.
object name = "Vinícius";    // Será do tipo 'object'.
```

---

## Nullabel Types

Nullabel Types (Tipos nulos).

### Void

Void (vazio), significa que não possui retorno algum, não é nada, é um espaço vazio.

### Null

Definições:

- ``Null`` significa _vazio, nada_.
- ``Null`` é **diferente** de zero ou uma string vazia.
- Todo _tipo_, **primitivo** ou **complexo** pode receber o valor ``null``.
- O _tipo_ deve ser marcado como ``Nullable Type``.
- É possível **atribuir** ``null`` a um objeto.
- Desde que o mesmo seja marcado como **nullable**.
    - Para marcar o _tipo_ como ``null``, deve-se utilizar uma _interrogação_ (**``?``**) na frente do _tipo_.
- Se uma "chamada" a um valor **nulo** for feita um _erro será apresentado_.

```
int? age = null;
```

---

## Alias

Definições:

- ``Alias`` é um "apelido" que _todo tipo_ no ``.NET`` tem.
- Por exemplo:
    - ``System.String`` tem o **alias** ``string``.
- Como o **C#** é _Case Sensitive_, tanto faz escrever o **nome do tipo** ou o **alias** (apelido).
- É recomendado usar _sempre_ o **alias**.
- No caso abaixo o resultado será o mesmo:
    ```
    int age = 25;    // Alias.
    int32 age = 25;  // Tipo.
    ```
    - Com o **alias** se escreve menos código.

---

## Valores padrões

Quando se define um _tipo_ (**built-in** - tipo padrão), ele sempre vem com um **valor padrão**, ele _nunca_ vem nulo.

Definições:

- Todo _tipo_ ``built-in``, já possui um **valor padrão**.
- Se nenhum valor for informado, seu **valor padrão** será utilizado.
    - ``int`` => 0.
    - ``float`` => 0.
    - ``decimal`` => 0.
    - ``bool`` => false.
    - ``char`` => '\0'.
    - ``string`` => "".

---

## Conversão implícita

