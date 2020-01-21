# Dicas do Terminal

Lista de alguns comandos do Terminal:

- `cd` <- Navega em Pastas
```
cd (...nome-da-pasta) <-- entra na pasta
cd /mnt/e <-- entra no disco E (usando windows)
cd.. <-- volta uma pasta
```

- `mkdir` <- Cria uma pasta no diretórito atual
```
mkdir (...nome)
```

- `ls` <- Lista o conteúdo da pasta atual
```
ls
```

# Dicas do Git

- `git init`(começar a seguir as pastas e arquivos de um projeto)
Esse comando nóa utilizamos para começar um projeto com o Git.
Chamamos a pasta do projeto de repositorio ou só repo. Para usar ele só entrar na pasta do seu projeto e executar assim:
```
git init
```

- `git status`(informa o estado do repo)
Usando o comando acima você terá como resultado informações de como esta o estado dos arquivos e pastas, na verdade você receberá informações apenas dos arquivos e pastas novos, removidos ou alterados.

- `git add`(segue os arquivos ou pastas no momento atual)
Com o comando `git status` você fica sabendo do rolê dos arquivos e pastas e com o `git add`você guarda esse momento dos arquivos e pastas para em seguida realizar o commit.

Comite: Se vc quer guardar o momento de todos os arquivos e pastas só executar o comando abaixo:
```
git add .
```

Mas se você quer pegar apenas alguns arquivos, você pode deixar o comando mais direto, dessa forma:
```
git add pasta/arquivo
```

- `git comit`(esse guarda momento atual)
Com o `comit`não é mais necessário ficar criando pastas old ou com datas bizarras. Ele é o cara que guarda o momento do seu repo.
A parte legal pe q vc deve e pode informar uma mensagem junto com momento atual para ficar mais fácil de acar esse estado se um dia precisar voltar nele. Ex:

```
git commit -m "Anotações do git até o commit"
```

- `git log`(listas dos estados que guardamos `comit`)
Com esse comando conseguimos ver todos os `commit`s que já fizemos na vida do repo que você estiver. =)