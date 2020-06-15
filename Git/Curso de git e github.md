
# Git comandos:
- `pwd`: mostra o local aonde vc está
- `cd`: cd + /nome da pasta que quer entrar.
- `ls`: lista todas as pastas.
- `mkdir`: cria uma pasta.
- `touch`: cria um arquivo.
    ```
    touch exemplo.txt
    touch teste/exemplo2.txt <- cria dentra da pasta teste
    ```
- `git status`: verifica oq tem no "container"
- `git commit -am "comentarios"`: ele adicona e commita no mesmo comando.

- `git log`: mostra todos os commits feitos com data e quem fez.
- `git log --online`: uma forma mais resumida do log.
- `git log --graph`: mostras as informações do log + o grafo
    - Nos git log o commit com um "(HEAD)" demonstra qual está sendo usado no momento.

- `git branch`: mostra onde está o (HEAD)
- `git diff`: mostra o q foi removido e o q foi adicionado na pasta.

- `git checkout master`: retorna para o ramo master.

- `git remote`: verifica se existe um repositório remoto.
- `git remote -v`: para ter mais detalhes do repositório.


# Instalando e configurando o git
- Baixar o git no site deles
- https://git-scm.com/download/win
- Instalar com tudo no padrão
- Uma das janelas vc pode escolher o editor de texto q vc vai querer usar

- Abrindo o git digite `git version` para ver a versão instalada
- `git config --global user.name "Por seu Nome"`
- `git config --global user.email "seu email"`
    - Vc pode digitar `git config user.name ou user.email` para verificar quais são.


- Click com o botão direito do mouse no icone do vsCode em propriedades pegue o caminho do executavel.
- Pesquise sistema no win e abra > configurações avançadas do sistema > botão: variáveis de ambiente > botão: novo
    - Nome da variavel: code
    - Valor da variavel: "colar caminho aqui"
    - Ok para aplicar.

# Criando repositorio local
```
git init
git add .
git commit -m "comentario"
```

# Rastrear mudanças e desfazer alterações 
```
- git log --online <-- pega o codigo do commit q vc quer
- git checkout ("bc4836c"<--codigo do commit a ser rastreado)

- git branch
- git checkout master <-- Retorna a ultima versão 

```

# Recuperar versões 

- Caso vc queria voltar as alterações feitas em um arquivo antes de commitar ele.
- `git checkout nomeDoArquivo.txt`

- Para remover as alterações feitas e depois de usado o git add mas antes do commit
- `git reset HEAD`

- Remover as alterações feitas depois do commit
- `git log --online` pegar o codigo do commit para qual voltar
- `git reset --hard (codigo do commit)`

# Criando ramificações no projeto
- `git checkout -b 'nome do ramo'`
- `git branch` --> para ver q está no ramo criado

# Unir o ramo master com o ramo criado
- `git merge 'nome do ramo'`

# Clonar repositório do github
- vá até o repositório no github, aperte o botão clonar e copie o endereço
- no terminal já na pasta a ser copiado o repositorio digite:
- `git clone (caminho copiado do github)`