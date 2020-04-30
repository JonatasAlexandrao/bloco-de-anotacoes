
npnjs.com => site para pesquisar as dependencias 

# Node
- node é um plataforma, programar em node é programar usando javaScript para o back end. Ele vai servir pra gente rodar o código sem um navegador.
- node é um grupo de APIs que vão servir pra gente rodar o js sem navegador.
  - O node usa o um "motor" chamado V8 o mesmo que é usado pelo navegador do google chrome.
  - HTTP
  - FileSystem

## NPN - Node Package Maneger
- ele é um gerenciador de pacotes, ele vai gerenciar todas as dependencias do nosso projeto.
- é por ele que vai ser instalados os pacotes via codigo no terminal.
- ele controla as dependencias e gerencia os pacotes.
- Software maiores.
  - mais estavel, gerenciado por uma comunidade muito grande.

## yarn
- é um concorrente do NPN feito pela empresa do facebook
- Ele tinha duas pricipais funcionalidades que o destacava, mas hoje não mais, são elas:
  - lock: ele servia para fechar a versão, travar a versão.
  - ele erá mais rápido.
- hoje em dia o NPN já tem um lock para travar versão e tem uma velocidade bem próxima a do yarn.
- Software menores.
  - mais rápido, tende a ter mudanças mais rápidas e inovações, gerido por uma unica empresa por isso ela escolhe o que faz com ele.

# Iniciando o Node no projeto

- pelo terminal já na pasta do projeto
- digite npm init
- package name: (nome-do-projeto) ---> se estiver correto "Enter"
- version: (1.0.0) ---> "Enter"
- description: descrição do projeto ---> "Enter"
- entry point: (index.js) --> aonde começa o projeto, caso seja no index.html é só digitar e "Enter"
- test command: ---> "Enter"
- git repository: (repositorio do git) ---> "Enter"
- keywords: ---> palavra chave do projeto. Ex.: se o projeto for open source é legal por aqui(se for vários separar por ","), "Enter"
- author: Jonatas --> "Enter"
- license: (isc)--> tipo da licensa, é mais para programas open sorce ou codigo livre (uma boa licensa é -- MPL-2.0), se for proprietario só "Enter"
- Se estiver tudo ok --> "Enter"


## Sistema de versão

- (1.0.'0') Terceiro numero da versão
  - patch: vc vai alteralo quando for feito uma pequena alteração, algo que não impacta diretamente como se usa o software. Correção de bug, refaturamento, melhorias de código.

- (1.'0'.0) Segundo numero da versão
  - minor: altera quando vc adiciona uma nova funcionalidade e mantendo a comptibilidade mas algo que não altera totalmente a forma de usar o software, nem algo muito grade.
    - correção de um grande bug.

- ('1'.0.0) Primeiro numero da versão
  - major: é uma grande alteração, algo que pode impactar na forma que esse software era usado antes.


## Instalar todas as dependencias de um projeto
  - No terminal: npm i

## Ignorando as dependencias para o git não upar elas
  - Na raiz do projeto criar um arquivo chamado .gitignore
  - Dentro dele digitar as pastas a serem ignoradas.
  - Nesse caso: node_modules