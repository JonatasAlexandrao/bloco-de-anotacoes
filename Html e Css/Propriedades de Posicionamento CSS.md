# Display:

# `display: inline`

1. Deixa elementos na mesma linha. 
2. As propriedade width e heigh não funcionam em display inline. Seu tamanho e altura são definidos pelo conteúdo que eles contém.
3. Ganham um comportamento de uma palavra. 

- Um componente com display: inline vai ignorar margens ao topo!


# `display: block`

1. O elemento passa a ocupar a linha toda, dessa forma não podendo ter outros elementos ao lado.
2. Permite definir width e height.
3. A maioria dos elementos vem por padrão com o display: block.

# `display: inline-block`


1. Permite definir largura e altura (essa é o único comportamento que é herdado do display:block).
2. Permite um elemento ao lado do outro (igual ao display:inline).
3. Ele também herda o comportamento de uma palavra (igual ao display:inline, por isso o espaço entre os elementos)
4. Por se comportarem como palavras podem ser afetadas pelo text-align.
5. Seu for usado o justify no text-align, para separar os elemento por igual na tela, lembrar q ele não justifica a ultima linha. Para resolver isso deve criar um :after no css q vai adicionar um texto na tela, ai vc faz ele ficar na ultima linha sozinho e o deixa sem conteúdo.
6. Por ele herdar o comportamento de palavra ele passa a ser considerado Conteúdo. Por isso se usado depois de um elemento com float ele ira ficar ao lado pois uma caraterística do float e não sobrepor conteúdo.

- `vertical-align`: serve para alinhar dois elementos que estão setados como display: inline-block. Eles serão alinhados por `top, middle...`
  
# `Display: flex`

- Tem um comportamento similar ao display:block.
- Quando vc usa um `display: flex` esse elemento se torna um 'flex container' e seus filhos 'flex item'
- esse elemento por padrão vai ter uma 'linha que vai da esquerda para a direita indicando a ordem para desenhar os filhos, chamado de `main axis`.
- cruzando o main axis temos o `cross axis` formando como um plano cartesiano onde o centro é o centro do elemento.
- main start: é onde começa o elemento (para o nosso idioma na esquerda).
- main end: é onde termina o elemento (para o nosso idioma na direita).
- cross start: na parte de cima a esquerda.
- cross end: na parte de baixo a esquerda.

1. O pai que tiver display:flex vai passar a mandar no posicionamento do filho.
2. O pai vai tentar fazer o filho preencher todo o espaço do pai, por isso o filho deve ter um tamanho definido.
3. Por padrão ele vai tentar apertar tudo em uma única linha, muitas vezes distorcendo e quebrando elementos para isso. Para permitir que haja quebra de linhas usasse a propriedade `flex-wrap`.

- `flex-wrap: wrap` : permite a quebra de linha, o padrão dessa propriedade é `nowrap`.
- `justify-content `: responsável pela posição horizontal dos elementos filhos. Ela trabalha com o eixo do ´main axis´.
- `align-items `: responsável pela posição vertical dos elementos filhos.

# `Display: inline-flex`

Semelhante ao `inline-blck`, é a junção das características do inline com o flex.

1. Usa o padrão do inline alinhando o texto a esquerda e no topo.
2. Permite adicionar os comportamentos do flex.

# Grid container
- Grid item: o conteúdo de dentro de cada quadrado.
- Grid line: linhas que fazem a divisão do grid.
- grid track: as colunas e as linhas dessa tabela.

    ## `Display:grid`

    ## `Display:inline grid`





-------------------------
-------------------------

# FLOAT

- Quando se usa essa propriedade criasse um novo contexto, como se fosse uma camada a frente da normal. O elemento passa a flutuar por cima.
- Se tivermos um <img> ou um display:inline ou um display:inline-block logo em seguida de um elemento com float, esse elemento vai se encaixar ao lado daqueles q estão flutuando. Se não couber ele fica logo abaixo.


`overflow: hidden`: tem o poder de esconder qualquer elemento filho que ultrapasse o tamanho do pai. Quando o pai não tem altura e largura definidas ele considera as dos filhos, mesmo q estejam em outro contexto.


`clear`: é usada para limpar o contexto caso tenho um elemento flutuando ao lado esquerdo(left), direito(right) ou ambos(both).

---------------------------
---------------------------

# POSITION

# `position: static`
    1. Static é o valor padrão dos elementos.
    2. Ela não se move.
    3. 


# `position: relative`
    1. Permite o uso de top e left.
    2. Usado na div pai para poder ser respeitada quando os filhos tiverem usando absolute. 


- `z-index`: move o elemento do eixo z (pode deixar algo a frente ou atrás um do outro). Seu valor padrão é 0. 

# `position: absolute`
    1. Quando usado cria um novo contexto levando o elemento para frente e o resto ocupa seu antigo espaço sumindo atrás dele.
    2. Usa como referencia de posicionamento o browser.


- `right, top, bottom e left`: podem ser usadas com o position, o único q não vai usa-las é o absolute q não se move. Usando um `position: absolute` e um `right: 0;` vc posiciona o elemento grudado a direita da tela, isso serve para os outros tb.

- `transform: translateX(-50%)`: usado junto com o `left: 50%` para centralizar uma div pelo seu centro.

# `position: fixed`
    1. Fixa a posição do elemento na tela, mesmo q o usuário role o scroll o elemento vai ficar no mesmo local em relação a tela.
    2. Seu alinhamento passa a usar como referencia o browser, logo se for usado um right:0 o elemento vai grudar a direita.


- `box-sizing: border-box`: quando usado um width: 100% significa q a largura vai ser o tamanho da largura do browser, porém caso vc tenha usado um padding(respiro interno) esse valor vai ser adicionado ao total (100% + 20px do padding). Para resolver isso deve se adicionar a propriedade `border-box` que vai limitar o elemento ao tamanho máximo do browser, quando usado o padding agora ele fará a conta diminuindo o tamanho do elemento e acrescentando o tamanho do padding para dessa forma ter o tamanho total sempre o mesmo.