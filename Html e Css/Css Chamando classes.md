# Nomenclatura de Classes:

  ## Classes de variação
  - Toda classe que começa com um `-` é uma variação (`.-second`). Já existe uma classe base e a variação apenas acrecenta e modifica o necessário para aquele elemento específico.
  - No css uma classe de variação deve ser chamada assim: `.button-store.-second`, dessa forma vc identifica que aquelas propriedades serão usadas apenas no elemento que tiver a classe principal junto da variação.

  ## Chamada especifica
  - `.header-store .action` colocar a class do elemento pai dar um espaço e colocar a class que vc quer trabalhar é uma forma de garantir que só vai ser alterado o elemento q tiver essa classe dentro daquele pai especifico. Isso tambem ajuda ao navegador ir direto onde esta a classe se não ele vai verificar todos os elementos do html para ver se algum usa aquela classe tb.

  ## Filho direto   
  - `.header-store > .navigation` colocar o simbolo de maior (>) indica que vc quer o elemento que tenha esse pai e seja filho direto dele. Significa que esse elemento não vai estar dentro de um outro elemento filho. É uma forma mais direta ainda de mostrar onde ele está para o navegador.
  - Aumenta a performace da pagina pq o navegador vai procurar somente dentro daquele pai e quando achar o primeiro filho com aquela classe vai parar.

  ## Próximo item abaixo
  - `.item.-star + .item `. O sinal de mais (+) representa o abaixo. Dessa forma ele só vai selecionar o elemento abaixo do `item.-star` logo a baixo dele que seja um `item`.
  - É uma forma de ter uma condição
  Ex.: esse .item tem um .item.-star antes dele? se sim ele faz o que foi posto nele.


  ## Pegando pelo tipo do input
  - `.header-store > input[type="search"]` ira selecionar o imput q seja filho do `.header-store` e que seja do tipo `search`.