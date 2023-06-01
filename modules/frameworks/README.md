# Frameworks

### Sumário:

- [Frameworks](#frameworks-1)
- [.NET Framework](#net-framework)
- [.NET Core](#net-core)
- [.NET Standard](#net-standard)
- [.NET 5](#net-5)
    - [.NET 5 - Futuro](#net-5---futuro)
- [LTS](#lts)
    - [Releases (Lançamentos)](#releases-lançamentos)
    - [Sigla LTS](#sigla-lts)
- [Versionamento](#versionamento)
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

**Standard** (padrão).

Definições:

- ``.NET Framework`` e ``.NET Core`` coexistem, muita aplicação que existe hoje foi escrita em ``.NET Framework`` e está sendo migrada para o ``.NET Core``.
    - Os dois **Frameworks** podem ser _instalados juntos_ (Side-by-Side).
    - Os dois **Frameworks** podem ser _utilizados_ no mesmo **projeto C#**, em que parte do _projeto_ é "antiga" e utiliza o ``.NET Framework`` é uma parte "nova" que utiliza o ``.NET Core``.

- Como garantir que um _código_ escrito **roda em ambos**? Vai ser **suportado** pelos dois **Frameworks**?
    - A partir do **``.NET Standard``** que garante que tudo escrito será **executado/rodado/compatível** tanto no ``.NET Framework`` quanto no ``.NET Core``.
    - O ``.NET Standard`` é a "**intersecção**" entre os dois **Frameworks**.
    > O ``.NET Standard`` estende também para vertentes, como um item criado em **C#** terá a garantia que vai funcionar no Windows, Web...
    - O ``.NET Standard`` não é um **Framework**, apenas um _contrato/definição_.
        - Conhecido com ``Surface API``.

![.NET Standard](https://learn.microsoft.com/pt-br/dotnet/standard/library-guidance/media/cross-platform-targeting/platforms-netstandard.png)

---

## .NET 5

### .NET 5 - Futuro

Definições:

- O ``.NET 5`` foi a _unificação_ dos **Frameworks** ``.NET Framework`` e ``.NET Core``.
- O ``.NET 5`` foi **retro compatível**.
- Essa mudança foi feita pois o ``.NET Core`` chegou ao ``.NET Framework`` em _nível de conteúdo_.
- Essa _unificação_ foi feita pois não fazia mais sentido ter **dois Frameworks**.

---

## LTS

### Releases (Lançamentos)

**Release** é uma _versão nova_ de algo do software, framework ou qualquer outra coisa. 

Definições:

- ``.NET Framework`` - Não possuia uma data de lançamento programada.
- ``.NET Core`` - Lançamentos (**Releases**) semestrais.
- ``.NET 5 e futuros`` - Lançamentos (**Releases**) anuais.

> Com **Releases** frequentes as mudanças são _menores_, com **Releases** com espaço de tempo maior as mudanças são _maiores_.

### Sigla LTS

Definições:

- Sigla para **Long Term Support** (Suporte de longa data).
    - A versão **``LTS``** deve ser utilizada em **produção**, pois será a **versão** garantida pelo _suporte_ da **Microsoft** por mais tempo. 
- ``.NET Framework`` - Todas as _versões_ eram ``LTS``.
- ``.NET Core`` - Todas as _versões_ com final ``1`` eram ``LTS``.
    - **1.1, 2.1, 3.1**...
- ``.NET 5`` e futuros - Versões maiores (**Major Version**).
    - **5, 6, 7, 8**...
    - Versões como 5.x, 6.x, 7.x **NÃO SERAM** ``LTS``.

> Opte **sempre** por ``LTS`` para _projetos em produção_. _Evite_ trabalhar em _produção_ com versões **beta** e **alpha**.

---

## Versionamento

