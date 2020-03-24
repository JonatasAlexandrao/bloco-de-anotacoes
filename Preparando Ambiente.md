# Preparando o Windows

1. Ir em atualização e segurança
2. aticar o "Modo de desenvolvedor

- no cmd digitar OptionalFeatures.exe
- Na janela selecionar o item "Subsistemas do windows para linux"
- reiniciar

# Instalar o Ubunto no win
- cmd digita "bash" vai aparecer uma mensagem com um link
- acessando o link vai abrir a loja do win e lá vc instala o ubuntu
- inicialize depois da instalação, pode demorar uns minutos, não fechar a janela q apareceu ela pode bugar ai é só clicar nela e dar um enter q ela volta 

# Instalar o hyper
- site: "hyper.is" baixar e instalar

# Instalar o ZSH
- no ubuntu digitar: sudo apt-get install zsh
- zsh --version (para verificar se ele está instalado)
- Caso usar outra versão linux: 
    https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH

# Configurar o ZSH como padrão
- abrir o terminal do ubuntu
- echo $SHELL --> mostra qual o shell q está sendo usado

Definir um novo sheel para minha conta de usuario:
- (which zsh --> mostra local q foi instalado)
- chsh -s zsh (caminho) 
OU
- chsh -s zsh $(which zsh)
    - Se não estiver funcionando tentar reiniciar o pc

# Instalando Oh My ZSH
- site: https://ohmyz.sh/
- Comando para instalar no terminal do ubuntu:
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Configurando o Hyper com ZSH
- Abrir o hyper
- Clicando no menu hamburguer a esquerda > edit > preferences
- No txt em fontSize: por 16 ao o tamanho q preferir.
- Pesquisar no texto por "shell" um pouco abaixo vai ter "Bash on Windwos", copia o caminho q tem ai e cola mais a baixo entre as aspas em "shell:'',"

- Mudando do bash para o ZSH
    - No terminal do ubuntu digite: "vim .bashrc"
    - aperte "i" para entrar em modo de insert
    - digite logo antes do ultimo comentario do começo da tela:
    "bash -c zsh"
    - depois aperte "esc" e digite ":x" e "enter" isso vai salvar e sair.


# Instalando o Live Server para atualizar automaticamente a pagina
 - procurar pela extensão: "live server"
 - com ela já instalada em baixo no canto direto vai ter um icone com uma escrita Go Live, só clicar ali q já esta funcionando
 - (Aula 09 - http na pratica)



# Vincular pasta com o github

- Criar a pastas no pc e criar o repositori no github
- Copiar o codigo do repositori criado
- ir com o hype até a pasta a ser vinculada
- digitar:
    - git init
    - git remote add origin (codigo copiado do repositorio)
    - git add .
    - git commit -m "frase explicando oq está sendo adicionado"
    - ai ele vai avisar q vc precisa passar o email e um nome é só copiar o codigo q ele mostra e colocar o email e depois o nome.
        git config --global user.email "you@example.com"
        git config --global user.name "Your Name"
    - git push -u origin master --> só na primeira vez 

# SSH gerar chave e terminar de vincular a pasta

- ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
- confima
- vc pode por uma senha

- vc deve ir até a pasta criada agora --> /home/k4bun/.ssh
- ls para ver o conteúdo
- cat id_rsa.pub
- copia o codigo q ira aparecer e cola no github na key

------------------------

git config creential.helper store
assim não precisa colocar user e senha