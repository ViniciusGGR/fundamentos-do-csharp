# Frameworks

### Sumário:

- [Frameworks](#frameworks-1)
- [.NET Framework](#net-framework)
- [.NET Core](#net-core)
- [.NET Standard](#net-standard)
- [.NET 5]()
- [LTS]()
- [Versionamento]()
- [Runtime e SDK]()

---

## Frameworks

Definições:

- **Framework** é uma _estrutura_, um _alicerce_.
    - Um conjunto de **bibliotecas** (muitas coisas podem ser _reutilizadas_).
- Utilizado como _base_ para **construir as aplicações**.
    - Com um **Framework** _não é necessário_ "fazer tudo, começar do zero".
- Conceito de **Framework** existente em _diversas tecnologias_.
- ``.NET`` (**dotnet**), um **Framework da Microsoft**. Criado e mantido pela **Microsoft**.
    - A ideia do **Framework** ``.NET`` é trazer _recursos comuns_ já prontos.
        - Itens do dia-a-dia.
        - Por exemplo: _Escrita de arquivo em disco_.
            - Acesso à dados (Banco de dados).
            - Criar um **Site**.
            - Criar uma aplicação **Desktop**.
            ...
    - Todos esses _recursos comuns_ já foram **validados** e **testados**.
    - Utilizar o **Framework** ``.NET`` _poupa muito tempo e reduz os riscos_ durante o desenvolvimento.

---

## .NET Framework

Definições:

- **C#** (C-Sharp) é a _linguagem de programação_ (você é **Programador C#**).
- O **Framework** se chama ``.NET`` (dotnet).
    - Teve sua primeira versão em meados de 2001.
        - Chamado de ``.NET Framework``.
    - Recebeu as versões 1.0, 1.1, 2.0, 3.0, 3.5, 4._x_ (Atualmente).
    - Pode ser _instalado_ **Side-by-Side** (Ter várias versões do ``.NET Framework`` lado-a-lado).
    - Compatível somente com **Windows** (_Não suporta_ Mac e Linux).
    - Considerado **legado** - (Softwares mais antigos - com anos no mercado).

---

## .NET Core

Definições:

- ``.NET Core`` é a **versão moderna** do ``.NET Framework``.
- Foi lançado em meados de 2015.
- Veio para _suportar_ outros **SOs** além do **Windows**, como Linux e Mac (Esses **SOs** não eram suportados no ``.NET Framework``).
- Suas primeiras versões continham apenas o básico.
    - **``Core``** significa _núcleo_, ou seja, o **essencial**.

    > O ``.NET Framework`` era utilizado por milhões de usuários (diversas aplicações escritas nesse **Framework**), portanto mudar um **Framework** (para o ``.NET Core``) usado por essa quantidade de usuários não é fácil.

    - O **Framework** ``.NET Core`` foi _totalmente reescrito_ (feito do "zero").
        - Isso permitiu que a **Microsoft** criasse até _compiladores_ novos em **C#**, tornasse o **C#** ainda mais _rápido_.
    - O ``.NET Core`` tem uma ótima **retro compatibilidade** (escrita quase não mudou, nomes de _bibliotecas_ foram mantidos...).
- ``.NET Core`` versão **3.1** está bem _estável_.
    - Muitas melhorias de _performance_ do ``.NET Core`` em relação ao ``.NET Framework``.
    - Versões **1.0, 1.1, 2.0, 2.1, 3.0, 3.1** (hoje o ``.NET Core`` já tem basicamente tudo o que o ``.NET Framework`` tinha).
    - Pode ser _instalado_ **Side-by-Side** (Ter várias versões do ``.NET Core`` lado-a-lado).

---

## .NET Standard

