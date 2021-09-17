
# Transform
  ## translate
  - `transform: translateX(100px)`: move para a direita, valores negativos moveriam para esquerda.
  - `transform: translateY(100px)`: move para baixo, valores negativos moveriam para cima.
  - `transform: translate(100px)`: move para baixo e para direita, valores negativos moveriam para cima e esquerda.

  ## scale
  - `transform: scaleX(1.5)`: aumenta o tamanho do item verticalmente, sendo 1 o tamanho original. Números abaixo de zero reduziram seu tamanho (0.5).
  - `transform: scaleX(1.5)`: aumenta na horizontal.
  - `transform: scale(1.5)`: aumenta proporcional.

  ## rotate
  - `transform: rotate(45deg)`: rotaciona o item (deg são graus). Pode se usar a medida turn (0.5turn) que significa volta, nesse caso 0.5turn é meia volta.

  ## skew
  - `transform: skewX(20deg)`:
  - `transform: skewX(20deg)`:
  - `transform: skew(20deg)`: 
    inclina o item. 



# Transition

  ```
  transition: opacity 300ms 200ms linear;
  ```

  - A propriedade transition é responsável por controlar a mudança de estado de um elemento, sua transição.
  O primeiro parâmetro é a propriedade que está sendo usada, o segundo o tempo que essa animação vai levar, o terceiro o tempo que ela vai esperar para começar assim que for ativada e o quarto o tipo de animação.


  ## TransitionEnd
  É um evento que é disparado quando uma animação termina.

  ## TransitionStart
  É disparado quando uma animação começa.

  ## transition-property
  Com ela vc escolhe qual propriedade que vai passar por uma transição.
  `transition-property: background-color, border-radius`

  ## transition-duration
  É quanto tempo essa animação ira durar.
  `transition-duration: 2s, 0.5s`
    Nesse exemplo a transição do background vai demorar 2s e a do border-radius 0.5s.
  
  ## transition-delay
  É o tempo que vc quer que a animação espere antes de começar.
  `transition-duration: 2s`

  ## transition-time-function
  São funções que já existem prontas no css
  - ease-in: dá uma suavizada no inicio da transição.
  - ease-out: dá uma suavizada no final da transição.
  - ease-in-out: sá uma suavizada tanto no inicio como no final da transição.
  - cubic-bezier(.15,.89,.85,.26): permite que vc personalize uma função alterando esses 4 números passadas a ela.

# Animation
  ## @keyframes
  Serve para criar animações.
  Dentro vc coloca as instruções como se fosse uma time line.

  ```
  @keyframes nomeAnimacao {
    0% {
      opacity: 1;
    }
    100% {
      opacity: 0
    }
  }
  ---------- OU -----------
  @keyframes nomeAnimacao {
    fron {
      opacity: 1;
    }
    to {
      opacity: 0
    }
  }
  ```

  Vc pode ir adicionando pontos em % e alterando o efeito em cada momento da animação.
  O fron(de) é o estado inicial.
  O to(para) é o estado final.

  - `Animation-name:` É o nome da animação, dada lá no @keyframes
  - `Animation-duration:` É a duração da animação. 
  - `Animation-iteration-count: infinite;`
    `Animation-iteration-count: 3;`: define quantas vezes a animação ira rodar, usando infinite ela ficara rodando em loop.

  - `Animation-delay: 2s`: tempo de espera antes de começar a animação.
  

  - `Animation:` Forma abreviada, o primeiro parâmetro é o name, o segundo duration...
  `Animation: nomeAnimacao 1s`

  ## Animation-direction
  - reverse: a animação ira de traz para frente.
  - alternate: a animação vai até o fim e depois volta ao contrario.
  - alternate-reverse: igual a alternate mas já começa vindo do fim pro começo.

  ## animation-fill-mode
  Define os valores aplicados antes e/ou depois da animação.
  - forwards: a animação ira até o final mas ficara lá não retornara ao seu estado original.
  - backwards: a animação ira para o inicio
  - both: é a junção das duas anteriores.

  ## animation-play-state
  Define se a animação está sendo executada ou se ela está pausada.
  - running
  - paused

  ## Animation-timing-function:
    Controla a velocidade que a animação será executada.
    Exemplo: começa mais rápido de repente fica bem lento e volta a ficar rápido no final.
    Existe algumas palavras chaves com tempos pre definidos:
      `Animation-timing-function: linear`
      `Animation-timing-function: ease-in`
      `Animation-timing-function: ease-out`
      `Animation-timing-function: ease-in-out`
      `Animation-timing-function: cubic-bezier(0.68, -0.6, 0.35, 1.6)`
  
    ### Animation-timing-function: cubic-bezier()
      `Animation-timing-function: cubic-bezier(.23,.97,.87,.19);` É a forma que vc altera esse tempo dentro da animação, existem sites onde vc escolhe como quer que fique a animação e depois só copia o código.
      - https://recursosfrontend.desenvolvimentoparaweb.com/

      - 🌐 Easing Functions Cheat Sheet
      https://easings.net/

      - 🌐 cubic-bezier.com
      https://cubic-bezier.com/

      - 🌐 Animista
      https://animista.net/

      - 🌐 Animatable CSS properties
      https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties



