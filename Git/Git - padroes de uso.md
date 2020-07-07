# Commit

1. Os commits devem ser feitos em inglêns.
2. As frases devem ser de forma imperativa.
3. Ter no maximo 50 caracteres.
4. Usar os gitmoji nos commits para facilitar o entendimento do que ele se trata. Ex.: existe um gitmoji para inicio de funcionalida, termino dela, em construção, bug ...
git mogihttps://gitmoji.carloscuesta.me/

  - Quando vc faz um commit ele cria um pacote de informações com ele, como Nome do Autor, um identificador, a data e a menssagem do commit.

# Branch
É uma ramificação, uma linha do tempo. O projeto inicia na branch master ela normalmente é a branch que está em produção sem erros funcionando. É comum se criar uma nova branch para iniciar uma nova funcionalidade, dessa forma não se altera o projeto que está funcionando e quando terminada pode ser unida com a master. É comum cada membro de uma equipe criar uma branch para mexer no projeto assim ninguem fica alterando trabalho um do outro.
- Juntar branch a master: git merge nomeDaBranch
- Deletar branch depois de ter juntado ela a master: git branch -d nomeDaBranch

- Antes de crear uma nova branch devesse fazer um `git pull` para atualizar e garantir q vc vai pegar a ultima versão da branch.

# WorkFlow
- É um fluxo de trabalho que deve ser seguido por todos os integrantes da equipe para uma melhor organização evitando assim um caos nos arquivos.

  ## GitFlow
    ### Branchs
      1. Master : É a branch que está em produção funcionando.
      2. Hotfix : É para correção de bug rápidos.
      3. Release: É um preparativo, vc passa tudo que está pronto da branch Develop e verifica se vai tudo funcionar só ai passa ela pra produção(master).
        - Quando já tiver algumas funcionalidades prontas vc pode criar uma branch na Release para testalas antes de mandar pra master, nesse caso a branch deve se chamar: git branch release/versao.
        - nesse momento pode se fazer commits mas só para documentação ou bug.
        - quando for unir a release com a master unir tb com a develop para que as duas fiquem do mesmo jeito.
      4. Develop: É a branch da qual todos os desenvolvedores vão criar suas branchs para iniciar o trabalho.
      5. Feature: Desenvolvendo uma funcionalidade, local de trabalho padrão.
        - Para criar a sua branch na Feature: git branch feature/nomeDaSuaBranch.
