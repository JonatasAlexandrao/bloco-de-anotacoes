# Grid Layout
O display grid veio para substituir o display flex-box
Vc usa ele no elemento pai e ele vai influenciar somente os filhos diretos. Vc define quantidade de linhas e colunas e usa isso para posicionar os filhos no grid, como uma tabela.

## exemplo e explicação
  https://www.origamid.com/projetos/css-grid-layout-guia-completo/
  https://www.youtube.com/watch?v=hKXOVD2Yrj8

## display: grid
  Esse código vai no elemento pai, mas só ele não vai mudar o comportamento dos filhos.

  ## grid-template-columns
  - `grid-template-columns: 200px 200px;`
  Essa propriedade seta as colunas no exemplo terão duas colunas cada uma de 200px.
  - Outra forma é fracionando as colunas, essa é uma nova forma de medida.
  Ex.: `grid-template-columns: 1fr 2fr 1fr`. Nesse caso o grid vai ter 3 colunas a primeira 1/4 do espaço a segunda vai ter o tamanho de 2/4 ou 50% e a ultima 1/4 tb.
  - Usando o display grid ele sempre vai respeitar o tamanho passado no columns, se por exemplo o conteúdo do filho for maior q o valor da coluna, ela não vai quebrar o conteúdo vai passar por cima da próxima coluna mas a coluna vai continuar tento o mesmo valor.
  - quando for usado o fr para escolher o tamanho da coluna o grid passa a respeitar o conteúdo do filho e nesse caso mesmo que vc tenha escolhido um valor pequeno em fr ele vai respeitar o conteúdo e ira crescer ignorado esse valor.

  ## grid-auto-columns
  Define o tamanho das colunas do grid implícitas(são as colunas que vc não estipulou um tamanho para elas) automaticamente
  ```
  grid-auto-columns: 100px; /* nesse caso as colunas geradas automaticamente terão 100px de largura */

  grid-auto-columns: 50px 100px; /* vc pode usar mais valores, nesse caso ele vai usar o 50px na primeira coluna criada automaticamente e o segundo na próxima e a seguinte volta pra 50px e depois 100px ... */
  ```

  ## grid-column ou grid-rown
  Serve para vc definir qual coluna ou linha o item deve ficar
  ```
  .item-6 {
    grid-column: 3; /*ele vai ficar na terceira coluna*/
    grid-column: 1 / 3 /* ele vai pegar da coluna 1 até a 3 */
    grid-column: 1 / -1 /* é uma forma de fazer o item pegar todas as colunas */
  }
  ```
    ### span
    `grid-column: span 2` /* o item vai expandir para duas colunas independente da onde ele começar */
    `grid-column: 2 / span 2;` /* vai começar da coluna 2 e expandir 2.

  ## grid-auto-rows
  Igual o do columns para rows
  `grid-auto-rows: 50px`

  ## grid-template-rows
  `grid-template-rows: 50px 100px`
  Controla o tamanho de cada linha do grid. No exemplo a primeira linha vai ter 50px, a segunda 100px, as seguintes vão seguir o tamanho do conteúdo como se fosse um auto.

  ## grid-auto-flow
  Define o fluxo dos itens no grid. Se eles vão automaticamente gerar novas linhas ou colunas.

  ```
  grid-auto-flow: column; 
  /* nesse caso em vez dele criar uma nova linha quando for criado um item que não cabe mais, ele ira criar uma coluna nova */
  ```
    ### grid-auto-flow: dense;
    Ele ira trocar os itens de lugares para q tudo se encaixe o mais sem espaço possivel.

  ## grid-template-areas
  Serve para definir areas para seu grid.
  ```
  .itemPai {
    grid-template-areas:
      "aaa bbb ccc"
      "ddd eee fff"
    ;
  }
  .umItem{
    grid-area: aaa;
  }
  ```
    Cada "" é uma linha do grid e cada palavra é uma coluna.
    Essas palavras servem para identificar qual conteúdo deve se posicionar naquele lugar, para isso pasta usar o grid-area no item e escolher sua posição.
 

  ### minmax()
    `grid-template-columns: minmax(200px, 1fr) 1fr 1fr;`
    Essa expressão serve para definir um valor mínimo e máximo para aquela coluna. Nesse caso a coluna nunca vai ter menos que 200px


    ### repeat()
    `grid-template-columns: repeat(3, 1fr);`
    É uma expressão para repitir o que foi passado "X" vezes. No exemplo ele vai criar um grid de 3 colunas cada uma com 1fr.
    ### auto-fit
    `grid-template-columns: repeat(auto-fit, minmax(100px, auto));`
    Coloca quantas colunas conseguir dentro do elemento, respeitando que cada uma tem que ter 100px.
    Usando ele o layout já fica responsivo.

    ### auto-fill
    `grid-template-columns: repeat(auto-fill, minmax(100px, auto));`
    Parecido com o auto-fit, mas quando o elemento pai for crescendo ele mantém o tamanho de todas as colunas e vai adicionando novas respeitando o tamanho passado mesmo se não tiver mais conteúdo para por nelas.

  ## gap
  `gap: 10px` é um espaçamento entre os itens do grid.
  `gap: 10px 5px` o primeiro é o espaço entre as linhas e o segundo o espaço entre as colunas.

  ## grid-template
  É a forma resumida para declarar area, coluns e row
  ``` 
  .teste {
    grid-template: 50px 1fr / 100px 1fr 100px
    /*primeiro vc define a linha depois a coluna*/
  }
  .teste2 {
    grid-template:
      "logo nav nav" 200px
      "sidenav content advert" 150px
      "sidenav footer footer" 100px 
      / 100px 1fr 50px;
  }
  /* no teste2 vc pode definir a area e logo em seguida passar o tamanho da linha no final depois da barra vc define o tamanho das colunas.

  ```

  ## grid
  Um atalho para definir todas as propriedades anteriores
  ```
  grid: 100px / 1fr 1f /* uma linha de 100px e duas colunas */
  ```

  ## justify-content
  Justifica os itens do grid em relação ao eixo x (horizontal).
  O valor padrão é o stretch.
  - space-between: vai dar espaçamento entre as colunas sem deixar espaço no inicio e final.
  - space-evenly: vai dar espaçamento igual incluindo o inicio e final.

  ## align-content
  Alinha os itens do grid em relação ao eixo y (vertical).

  ## justify-items
  Justifica o conteúdo dos itens do grid em relação ao eixo x.

  ## align-items
  Alinha o conteúdo dos itens do grid em relação ao eixo y.

  ## justify-self
  Ele é igual o justify-items mas para um item só, então vc define ele dentro do item q vc quer alterar.

  ## align-self 
  Igual oa align-items mas apenas para um item.
  



