# Linguagens e Compiladores

### Sumário:

- [Linguagens de programação](#linguagens-de-programação)
- [Alto e baixo nível](#alto-e-baixo-nível)
- [Linguagem compilada e interpretada](#linguagem-compilada-e-interpretada)
    - [Linguagens Compiladas](#linguagens-compiladas)
    - [Linguagens Interpretadas](#linguagens-interpretadas)
- [Compilada e Interpretada]()

---

## Linguagens de programação

Uma linguagem de programação é a forma (**Comunicação**) como dizemos para o computador como executar algo.

Computadores usam _binário_ (``0`` e ``1``) para comunicação/operação serem executadas no processador (CPU), GPU, memórias...

As linguagens de programação (LP) fazem o intermédio entre os desenvolvedores e computadores.

Tudo o que for escrito em uma LP será traduzido para _binário_ (linguagem de máquina).

Este processo de "_tradução_" é conhecido como **compilação**.

Existem várias linguagens de programação:
- Cada uma com seu _compilador_.
- Cada _compilador_ trabalha de uma forma.

> **Compilador** - Agente que executa a compilação, que é a transformação do texto escrito para _binário_ (0 e 1).

---

## Alto e baixo nível

Ao enviar uma instrução ao computador estamos falando em nível de máquina (baixo nível).

Estas instruções sempre serão no formato binário (``0`` e ``1``).

Quanto mais detalhada a necessidade, mais baixo o nível.

As linguagens mais modernas como C#, Java, Dart, PHP... são consideradas de **alto nível** (mais próximo do usuário/devs).

- Um exemplo de uma linguagem de programação de baixo nível é o **Assembly**.

Quanto mais específico você precisa ser ao escrever o código, mais **baixo nível** é preciso descer.

Linguagens de **alto nível** já fornecem acesso à tudo que é preciso a nível de hardware já pronto.

---

## Linguagem compilada e interpretada

### Linguagens Compiladas:

Dada quando existe o processo de _compilação_ da mesma.

- Consiste em receber um arquivo texto e convertê-lo para binário.
    - Normalmente otimizado para leitura de humanos.

### Linguagens Interpretadas:

- Arquivo de texto.
    - Lidos e _interpretados_ por um **intérprete**
    - Feito em _tempo de execução_.
- **JavaScript** é _interpretado_.

Esses _arquivos de texto_ **NÃO** são convertidos para binário.

> **Tempo de Execução**: É o que acontece durante a execução do código pelo computador ou interpretador.

- No caso do **JavaScript**:
    - O navegador normalmente é escrito em uma linguagem de _alto nível_.
    - Possui um _interpretador_.
    - Lê e executa um arquivo de texto **JavaScript** em tempo real.

---

