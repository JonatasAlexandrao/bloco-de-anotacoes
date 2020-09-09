# Seletores de Classes:
  - 30 seletores css
  https://code.tutsplus.com/pt/tutorials/the-30-css-selectors-you-must-memorize--net-16048

  ## Classes de variação (.-A)
  - Toda classe que começa com um `-` é uma variação (`.-second`). Já existe uma classe base e a variação apenas acrecenta e modifica o necessário para aquele elemento específico.
  - No css uma classe de variação deve ser chamada assim: `.button-store.-second`, dessa forma vc identifica que aquelas propriedades serão usadas apenas no elemento que tiver a classe principal junto da variação.

  ## Chamada especifica (.A .b)
  - `.header-store .action` colocar a class do elemento pai dar um espaço e colocar a class que vc quer trabalhar é uma forma de garantir que só vai ser alterado o elemento q tiver essa classe dentro daquele pai especifico. Isso tambem ajuda ao navegador ir direto onde esta a classe se não ele vai verificar todos os elementos do html para ver se algum usa aquela classe tb.

  ## Filho direto (A > B)
  - `.header-store > .navigation` colocar o simbolo de maior (>) indica que vc quer o elemento que tenha esse pai e seja filho direto dele. Significa que esse elemento não vai estar dentro de um outro elemento filho. É uma forma mais direta ainda de mostrar onde ele está para o navegador.
  - Aumenta a performace da pagina pq o navegador vai procurar somente dentro daquele pai e quando achar o primeiro filho com aquela classe vai parar.

  ## Próximo item abaixo (A + B)
  - `.item.-star + .item `. O sinal de mais (+) representa o abaixo. Dessa forma ele só vai selecionar o elemento abaixo do `item.-star` logo a baixo dele que seja um `item`.
  - É uma forma de ter uma condição
  Ex.: esse .item tem um .item.-star antes dele? se sim ele faz o que foi posto nele.

  ## Seletor irmão (A ~ B)
  - `.header ~ .title` bem semelhante ao seletor de proximo (A + B), porém ele seleciona todos os elementos diretos e não só o primeiro.


  ## Seletor por contexto (A[propriedade])
  - `A[alt]` nesse exemplo ele vai selecionar todos os elementos com a classe A que tenham definido a propriedade alt.

  - Pegando pelo tipo do input ([type=''])
  - `.header-store > input[type="search"]` ira selecionar o imput q seja filho do `.header-store` e que seja do tipo `search`.

  - `A[href*='trecho']`: selecionara os links que tiverem pelo menos esse 'trecho'.
  - `A[href^='inicio']`: selecionara os links iniciados com esse trecho.
  - `A[src$='final'`: apenas os com final igual ao trecho.

  ## Selecionar todos menos um (A:not(B))
  - Seleciona todos os elementos de classe A menos aquele q vc passar.

  ## Selecionar o primeiro ou ultimo filho (A:first-chld / A:last-child)
  - Seleciona o primeiro ou ultimo filho.

  ## Interações com o checked do radio e checkbox
  - `A:checked`

  ## Selecionar elemento da posição N
  - `A:nth-child(n)` Seleciona o elemento na posição indicada pelo argumento n. Se for passado o número 2 ele ira selecionar o segundo elemento daquele conjunto.
  - `:nth-child(3n)`Podemos criar uma expressão, onde todos os elementos múltiplos de 3 seriam selecionados (3,6,9...).