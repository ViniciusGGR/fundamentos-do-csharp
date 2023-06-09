# C#

### Sumário:

- [Por que utilizar C#?](#por-que-utilizar-c)
    - [Por que aprender C#?](#por-que-aprender-c)
- [C# como primeira linguagem](#c-como-primeira-linguagem)
- [Código gerenciado](#código-gerenciado)
    - [Definições - Código Gerenciado](#definições---código-gerenciado)
- [Compilação e gerenciamento](#compilação-e-gerenciamento)
- [IL](#il)

---

## Por que utilizar C#?

Pronúncia - "C-Sharp".

Definições sobre o **C#**:

- Linguagem de Programação.
    - **Tipada**, **compilada** e _gerenciada_.
- Criada por Anders Hejlsberg (criador também do _Delphi_ e do _TypeScript_).
    - Em meados de 2001.
- "Principal" linguagem da **Microsoft**.

### Por que aprender C#?

Definições:

- Uma das Linguagens mais completa do mercado hoje.
    - Como o **C#** faz parte do ecossistema da **Microsoft**, a linguagem pode ser utilizada na criação de: _Aplicações Web, Aplicações Desktop, Aplicações Mobile, Machine Learning, Data science, games (Unity), IoT_...
- Maturidade.
    - Muito conteúdo disponível online sobre o (**C#** e **.NET**).
- Mercado.
    - Muitas vagas de emprego disponíveis.
    - Mercado com foco em _empresas maiores_ (enterprise).
- Comunidade.
    - Comunidade grande e muito forte.
- Aplicabilidade.
- **Microsoft** por trás.
- Orientação à Objetos.

---

## C# como primeira linguagem

Definições:

- Não é a _linguagem_ mais fácil.
- Focada em **OOP** (Orientação à Objetos) - _Base da programação_.
    - Tem também a **Programação Funcional**.
- **OOP** vai te dá a "base" para _aprender coisas novas_.
    - Quanto "mais tempo" na _base_, "mais fácil" aprender coisas novas.

> **Dica**: A _linguagem_ mais "**fácil**" no começo pode te prejudicar no final.

---

## Código gerenciado

Definições sobre C#:

- É uma _linguagem **tipada**_.
- É **compilada**.
- De _código gerenciado_.

### Definições - Código Gerenciado

- É uma _linguagem_ em que sua "execução" _depende_ de um **gerenciador**.
    - Também conhecido como **Runtime**.
    - No caso do **C# (.NET)** este **Runtime** se chama **``CLR``** ou **``CLR Runtime``**.
- O **``CLR``** gerencia _memória_, _segurança_, entre outros _recursos básicos_.

> **``CLR``**: É uma sigla para _Common Language Runtime_ ou (**gerenciador de linguagem comum**).

Definições:

- Em linguagens como C/C++ por exemplo, a _alocação de memória_ é feita **manualmente**.
- A "tela azul do Windows" ocorre na maioria das vezes porque algum programa tentou acessar algum lugar da _memória_ que estava "reservado" **exclusivamente** para o _Sistema Operacional_ (S0).
- Quando se tem um **gerenciador** (Runtime), interagimos menos ou quase não interagir com _recursos da máquina_ e o desenvolvimento fica _mais "rápido e seguro"_.

---

## Compilação e gerenciamento

Definições:

- A **Microsoft** possui outras _linguagens_ como ``VB.NET``, ``F#`` e até ``Cobol.NET``.
- Todas essas _linguagens_ precisam ser mantidas.
    - **Manutenção de código** mesmo, _correções de bugs_ e afins são tarefas que a **Microsoft** tem que executar com frequência nessas _linguagens_.
- Quando o "ecossistem" de desenvolvimento **Microsoft** foi criado ele foi _pensado_ desta forma:
    - Dar **suporte** a _várias linguagens_.
- Se cada _linguagem_ tivesse um **gerenciador**, isto seria muito complicado de manter essas _linguagens_.

A **Microsoft** pensando nessa melhor **Manutenção de código** dessas _linguagens_ criou um **ecossistema** onde:

- Os **compiladores** ficam _separados_.
    - Um para cada _linguagem_ (Ou mais de uma _linguagem_).
    Cada linguagem terá suas caracteristicas "únicas".

- A **compilação** inicial gera um _código intermediário_.
    - **Intermediate Language** (``IL``).
    - Essa **compilação** inicial _não gera_ o código final (**binário** (0 e 1)).

> **``IL``**: Sigla para **Intermediate Language** ou (_linguagem intermediária_).

Resumindo: Quando um código **C#/F#/VB.NET** é **compilado** ele é "traduzido" para uma **Intermediate Language** (``IL``) e só depois ele é _realmente_ **compilado**. Isso faz com que se tenha apenas um **gerenciador** para todas essas _linguagens_ e permite a utilização de diferentes tipos arquivos dentro do mesmo **projeto**.

---

## IL

Definições:

- Embora as **compilações** sejam diferentes em cada _linguagem_:
    - O **gerenciamento** é igual.
    - Alocação de memória é igual.
    - Execução de instruções no processador é igual.
- O ``CLR`` **compila** para _código de máquina_ (**binário**), executa e gerencia.
    - Qualquer _linguagem_ suportada no ecossistema Microsoft: **C#**, **VB.NET**, **F#**, **Cobol.NET**.
- Por conta da ``IL`` é possível ter _arquivos_ **C#** e **VB.NET** no _mesmo projeto_ (Nota: Não é uma prática recomendada ter arquivos de _linguagens_ diferentes no mesmo projeto).
    - Mas **nunca** no mesmo arquivo.
- O resultado da **compilação** do ``IL`` é sempre o mesmo (o código **binário** será igual), independente da _linguagem_ escolhida.

``Código: C#, VB.NET, F#, Cobol.NET``    **---->**    ``"Traduzido" para Intermediate Language (IL)``    **---->**    ``Gerado Código Binário (0s e 1s)``.

> O processo de **conversão** do ``IL`` para **binário** é conhecido como ``JIT`` - Sigla para **Just in Time**.

``IL`` é uma **linguagem intermediária** na qual todas _linguagens_ da **Microsoft** são **compiladas**.

---