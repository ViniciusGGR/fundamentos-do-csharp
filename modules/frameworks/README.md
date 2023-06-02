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
    - [Versionamento de Software](#versionamento-de-software)
- [Runtime e SDK](#runtime-e-sdk)
    - [Runtime](#runtime)
    - [SDK](#sdk)

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

### Versionamento de Software

Definições:

- **Versão Semântica** é _dividida_ em fases:
    - 1º Fase: **Alpha** - Tá longe de ter uma versão "**final**".
    - 2º Fase: **Beta** - Versão de "_testes_" de um software, linguagem ou framework. Esse produto já está funcionando (com "bugs" provavelmente), mas que dá uma ideia inicial.
    - 3º Fase: **Release Candidate** - Uma versão "_candidata_" a ser a versão "**final**". Os "bugs" já foram corrigidos, com os nomes todos corretos (_provavelmente_ será a **versão final**).
    - 4º Fase: **Final**.
- Todo esse **versionamento** é dado por _números e letras_.
- O **versionamento** é dividido em _três partes_:
    - ``Major``: Primeiro número, **release** maior.
        - ``5.1.2`` para ``6.0.1``.
    - ``Minor``: Segundo número, **mudanças pequenas/leves**. Essas mudanças podem "quebrar" a aplicação, mas nada que não possa ser corrigido.
        - ``3.1.2`` para ``3.2.2``.
    - ``Patch``. Terceiro número, **correções de bugs** na versão atual.
        - ``3.1.2`` para ``3.1.3``.

Exemplos:

- ``15.8.2`` - Versão **15** com **8** mudanças significativas e **2** correções de bugs.
    - ``15`` - Major.
    - ``8`` - Minor.
    - ``2`` - Path.
- ``0.0.1`` - Versão **alpha** (versão inicial).
- ``1.0.2-rc1`` - "**rc'**" significa _release candidate 1_ uma possível **versão final**.

> **Nota**: Normalmente uma _versão final/oficial_ começa com ``1.0.0``;

Definições:

- Versão ``15.8.2``:
    - **MAJOR** (``15``): Pode conter "incompatibilidade" com **versões anteriores**.
        - Chamadas de _Breaking Changes_ (Quebra de código).
    - **MINOR** (``8``): Possui mudanças mas é **totalmente** compatível com **versões anteriores**.
        - _Backward Compatibility_ (Versão compatível com **versões anteriores**).
    - **PATCH** (``2``): Correções de "bugs" e outros itens simples (mudanças não tão significativas).

Definições:

- ``Alpha``: Ainda não sabe como vai ser as coisas.
    - Muito ainda pode mudar.
- ``Beta``: Já tem ideia da estrutura.
    - As coisas ainda podem mudar.
- ``Release Candidate``: Candidato a versão final.
- ``Final``: Versão Final.

- Utilizando "_anotações_" como:
    - ``Alpha`` -> ``0.0.1-a1``.
    - ``Beta`` -> ``0.0.2-b1``.
    - ``Release Candidate`` -> ``1.0.0-rc1``.
    - ``Final`` -> ``1.0.0``.

    > Normalmente **alpha** e **beta** tem _versões menores_ que ``1.0.0``.

---

## Runtime e SDK

### Runtime

O **Runtime** faz o _gerenciamento_ da aplicação.

Definições:

- O **Runtime** é necessário para _executar/rodar/gerenciar_ aplicações **C#**.
- Aplicações ``.NET`` inicialmente são divididos em 3:
    - ``ASP.NET`` é uma tecnologia dentro do ``.NET`` para criar aplicações **Web**.
    - ``Windows Forms`` para criação de aplicações **Desktop**.
    - ``.NET Core`` para criar qualquer outra aplicação.
        - **Console**, **Batch**, **Serviço**.
        - Aplicações que não possuem uma _interface gráfica_ (GUI) por exemplo.
    - O ``.NET``, ``ASP.NET``, ``Windows Forms``, ``.NET Core`` tem diversas **versões**.
        - A versão desses **Frameworks** tem que ser _compatível_ com a versão utilizada durante a **codificação**.
        - Por exemplo, codificando com o **C# 12**, é necessário utilizar o ``.NET 8`` e assim por diante.
    - O **Runtime** só _roda as aplicações_, apenas executa após a **compilação** para uma (linguagem de máquina).
    - O **Runtime** tem um _tamanho menor_, é **otimizado para execução**.

### SDK

Definições:

- Sigla para **Software Development Kit** (Kit para desenvolvimento de software).
    - Traz compilador, suporte a sintaxe do **C#** e várias ferramentas que ajudam durante o desenvolvimento.
- Possui tudo o que é preciso para **criar aplicações**.
- O ``SDK`` já vem com o **Runtime** _integrado_.
    - Não é possível instalar o ``SDK`` sem o **Runtime**.
- O ``SDK`` **não deve** ser utilizado em "_produção_".
    - Para "_executar_" só é necessário o **Runtime**.
    - Em "_produção_" só deve ser instalado o **Runtime** do ``.NET`` para execução da aplicação.
- O tamanho do ``SDK`` é muito maior do que o **Runtime**.
    - O ``SDK`` permite o desenvolvimento de _softwares_ utilizando **C#**, ``ASP.NET``, ``.NET``...

---