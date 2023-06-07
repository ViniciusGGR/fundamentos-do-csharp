# .NET

### Sumário:

- [Instalação](#instalação)
- [dotnet cli](#dotnet-cli)
    - [Definições - dotnet CLI](#definições---dotnet-cli)
- [VS Code](#vs-code)
- [Tipos de projeto](#tipos-de-projeto)
    - [Criando um novo projeto com .NET](#criando-um-novo-projeto-com-net)
- [Fluxo de execução](#fluxo-de-execução)
    - [Comandos principais do ``.NET``](#comandos-principais-do-net)
- [Variáveis de ambiente](#variáveis-de-ambiente)
    - [Comando ``dotnet run``](#comando-dotnet-run)
- [Estrutura do App](#estrutura-do-app)
- [Debug]()

---

## Instalação

- [Tutorial de Instalação e Configuração do .NET](https://balta.io/blog/dotnet-instalacao-configuracao-e-primeiros-passos)
- [Link para download do .NET](https://dotnet.microsoft.com/pt-br/download)

Para verificar a instalação do ``.NET`` no **Windows/Linux/macOS**, digite o seguinte comando no _terminal_:

```
dotnet --version
```
```
>> Retorna: A versão do '.NET' instalada
>> 7.0.203
```

---

## dotnet cli

Definições:

- Sigla para **Command Line Interface** (Interface de Linha de Comando).
    - **Comandos** adicionais integrados ao _terminal_.
    - O ``dotnet --version`` é um **comando do ``CLI``**.

Quando instalado o ``.NET``, o ``CLI`` é instalado junto.

### Definições - dotnet CLI

- Definido pelo **comando** ``dotnet``. Todos os _comandos_ que comecem com ``dotnet `` está executando o **dotnet CLI**.
    - O **comando** ``dotnet --version`` - Verifica a _versão atual_.
    - O **comando** ``dotnet --list-sdks`` - Lista os ``SDKs`` _instalados_.
    - O **comando** ``dotnet --list-runtimes`` - Lista os ``Runtimes`` _instalados_.
    - O **comando** ``dotnet help`` - Exibe a **ajuda** e Lista de **comandos** _disponíveis_.

> **dotnet CLI** é uma _integração_ que o ``.NET`` traz com a **linha de comando**.

Os **comandos** podem ser executados no _Windows Terminal_, _CMD_, _Windows PowerShell_, _terminal do Linux/macOS_...

---

## VS Code

O ``VS Code`` (Visual Studio Code) é um _editor de código_. O ``VS Code`` tem o "melhor" **suporte para C#**, é desenvolvido pela **Microsoft**, tem atualizações frequentes, possibilita a criação de **pacotes** próprios, diversos _temas_...

O **Visual Studio Community** é uma ``IDE`` (Ambiente de Desenvolvimento Integrado). Uma ``IDE`` é mais completa que um _editor de código_, mas consome muito mais recursos da sua máquina.

- [Instalação do **VS Code**](https://code.visualstudio.com/)
- [Artigo - Visual Studio Code: Instalação e Customização](https://balta.io/blog/visual-studio-code-instalacao-customizacao)

O ``VS Code`` tem diversas **extensões** disponíveis para instalação, e essas **extensões** ajudam na _produtividade_ no dia-a-dia de desenvolvimento.

> Lembre-se de **instalar** a _extensão_ do **C#** (ms-dotnettools.csharp) no ``VS Code``.

- O _comando_: ``Ctrl + ,`` abre as **configurações** do VS Code.
- O _comando_: ``Ctrl + Shift + P`` abre os **comandos** disponíveis no VS Code.
- O _comando_: ``Ctrl + B`` abre/fecha a **barra lateral** do VS Code.
- O _comando_: ``Ctrl + Shift + '`` abre o **terminal** do VS Code.

---

## Tipos de projeto

O ``.NET`` é um **Framework** para criação de _aplicações_ utilizando as **linguagens/ecossistema da Microsoft**, permitindo a criação de _projetos_ vários "tipos", como _projetos_ web, API, Machine Learning... Cada _projeto/aplicação_ criada com ``.NET`` é preciso "especificar" o **tipo de projeto** e com isso cada projeto tem um _resultado final diferente_.

Definições:

- Projeto do tipo: **Class Library** (Biblioteca de Classes)
    - O resultado final é uma **DLL**.
    - Não possui interface.
- Projeto do tipo: **Console Application**
    - O resultado final é uma **apicação que roda no terminal/console** (um arquivo executável ``.exe``).
    - Pode receber _dados_, esperar _input do usuário_.
    - Tem uma _"interface" básica_, na qual o usuário pode interagir.
- Projeto do tipo: **Web**
    - ``ASP.NET`` Web.
    - ``ASP.NET`` MVC.
    - ``ASP.NET`` WebAPI
- Projeto do tipo: **Testes**
    - Microsoft Tests
    - Projeto de **Teste** são utilizados para _testar_ as **aplicações** antes de enviar para os clientes e deixar todos os **testes automatizados**.

### Criando um novo projeto com .NET

Definições:

- Criando um _novo projeto_ utilizando o **dotnet cli**, com o comando ``dotnet new``:
    - ``dotnet new console`` -> Novo **Console Application**.
    - ``dotnet new classlib`` -> Nova **Class Library**.
    - ``dotnet new web`` -> Novo projeto ``ASP.NET Core``.
    - ``dotnet new mvc`` -> Novo projeto ``ASP.NET Core``
    - ``dotnet new webapi`` -> Novo projeto ``ASP.NET Core``.
    - ``dotnet new mstest`` -> Novo projeto **Microsoft Test**.

O _comando_ ``dotnet new typeOfProject`` cria a **estrutura inicial** da _aplicação_.

- Com o ``dotnet new`` _criar um projeto_ é o mesmo que **gerar os arquivos iniciais** de uma _aplicação_.
- O ``dotnet new`` vai "sempre" gerar os arquivos na _pasta atual_.
- Para _especificar_ uma pasta, utilize o ``-o``.
    - ``dotnet new console -o MeuApp``.
        - Esse comando vai criar uma _nova pasta_ chamada **MeuApp** com os arquivos dentro.

- O comando ``mkdir NewFolderName`` cria uma **nova pasta** no seu diretório atual.
- O comando ``cd FolderName`` **acessa/entra** na pasta especificada no comando.
    - O comando ``cd ..`` volta para o diretório anterior ao atual.
-O comando ``ls`` **lista todos os arquivos** dentro da pasta/diretório atual.

> O comando ``dotnet new console -o FirstApp`` **cria uma nova aplicação** do _tipo console_ dentro de uma **nova pasta** chamada ``FirstApp``.

---

## Fluxo de execução

### Comandos principais do ``.NET``

Definições:

- ``dotnet restore``: _Restaura todos os pacotes_ que a **aplicação** precisa para ser executada.
    - A primeira coisa a ser feita quando pegar uma aplicação ``.NET`` é executar o **comando** ``dotnet restore``, para que ele baixe todas as _dependências/pacotes_ que essa aplicação precisa para ser **executada**.
- ``dotnet build``: _Compila_ a **aplicação**.
    - Ao executar esse comando o ``.NET`` pode gerar mensagens de "alerta" e "erros" na **aplicação**.
- ``dotnet clean``: _Limpa_ as **compilações** anteriores.
    - Esse **comando** _limpa todos os arquivos de cache_ da aplicação.
    - Uma **boa prática** é executar um ``dotnet clean`` _antes de executar_ um ``dotnet build``.
- ``dotnet run``: _Compila_ e _executa_ a **aplicação**.

> Um _projeto_ ``.NET`` deve possuir um _arquivo_ com a **extensão** ``.csproj``.

---

## Variáveis de ambiente

Definições:

- É comum ter vários _ambientes_ para **aplicações**, ou seja, onde as _aplicações_ estão **rodando**.
    - **Ambiente de Desenvolvimento**: É a sua máquina, onde as _aplicações_ estão sendo _desenvolvidas/criadas_.
    - **Ambiente de Homologação/Testes**: É um _ambiente de teste_, esse ambiente é "fora da sua máquina" e o mesmo é responsável por **testar** as _aplicações_.
    - **Ambiente de Produção**: É o **servidor** onde a _aplicação_ está "_rodando_" para os usuários, pode-se dizer que é o "**ambiente final**".
- Cada _ambiente_ possui suas **configurações/variáveis** próprias. Isso é conhecido como ``Variáveis de Ambiente``:
    - Chaves de acesso externo _específicas_.
    - Conexões com bancos de dados (BDs específicos).

### Comando ``dotnet run``

Com o **comando** ``dotnet run`` é possível dizer ao ``.NET`` qual _ambiente está sendo utilizado_:

- ``dotnet run --environment=$SEU_AMBIENTE``.
    - ``dotnet run --environment=development``. Isso garante que o desenvolvedor está no _ambiente de desenvolvimento_.
    - ``dotnet run --environment=production``. Isso garante que o desenvolvedor está no _ambiente de produção_.
- O comando ``run`` _não executa_ **depuração** (``Debug``) para detecção de erros.
    - Neste modo a _aplicação_ não vai parar nos **Break Points**.

---

## Estrutura do App

