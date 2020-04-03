
# API do DOM

São comandos, mas não são do javaScript.
Serve para acessar os recursos do browser
API é o meio do caminho aonde, nesse caso fica entre o javaScript e o navegador.

# Arrow Function
() => {}

- Caso precise q a finction tenha um nome para poder ser chamada em outro lugar vc pode atribuir uma variavel para ela.
Se não for passado um parametro quando chamada a função ela simplismente passa vazio.

    ```
    const create = (name) => {...}
    ```

- Caso só tenha o valor de retorno dentro da function podesse retirar a palavra chave "retorn", podesse tirar as chaves tb.


# If ternário
O if ternário é um if de uma unica linha que retorna um valor. Parecido com if do excel.

- como ele retona um resultado vc pode usar uma variavel pra guarda-lo.
No exemplo está sendo testado se o nameClass é igual a string. Depois do "?" vem o valor a ser retornado para a condição verdadeiro e depois do ":" o resultado para a condição falça.
    ```
    nameClass == "-front" ? "icon-c.png" : "icon-gg.png"
    ```

# Component Stateless
É um componente "burro", que não sabe fazer as coisas sozinho. Todos os dados devem ser passados pra ele por parametro, ele só guarda estrutura, layuot e comportamentos.

# Variaveis
Variáveis com $ antes indicam que são elementos pegos do html.

- `const`: é um tipo de variável que não pode ser alterada. Muito boa para adicionar elementos do html.

- `let`: uma variável que só funciona no contesto atual.

# Template Strings
"<img class = 'icon' src='img/icon-collabcode.png' alt='Gueio mascote da CollabCode'>"

`<img 
class = 'icon' 
src='img/icon-collabcode.png' 
alt='Gueio mascote da CollabCode'
/>`

Adicionando crase no lugar das aspas vc pode quebrar a linha da string quantas vezes quiser.

# Interação com o HTML

- Pegando elemento:
    - `document.querySelector("")` : pega um elemento do html com uma class ou id passado entre "".
    Cria-se uma variável e adiciona o elemento dentro dela.
    
    ```
    const $root = document.querySelector('#root')
    const $root = document.querySelector('.root')

    usasse . para class e # para id

    ```

    ## Adicionar propriedades ao elemento
    - Adicionando Class: `$elemento.classList.add("exemplo-class")`


# Criando elementos novos no HTML

- Dê um nome para chama-lo no js e passe a tag a ser criada: `const $memoryCard = document.createElement("article")`.

    ## Inserindo o elemento criado no html
    `$root.insertBefore($memoryCard, null)`
    Adicionando o elemento: 
    o $root é o elemento pai.
    Como parametro vc passa o elemento e o segundo parametro e depois de qual elemento, pode se passar null para nem um elemento.
    
    - `insertAdjacentHTML`: adicionar um elemento usando codigo html.
    Como parametro vc passa a posição e o elemento a ser adicionado.
    As opções de posição são:
        - 'beforebegin'
            Antes do elemento.
        - 'afterbegin'
            Dentro do elemento, antes de seu primeiro filho (childNode).
        - 'beforeend'
            Dentro do elemento, após seu último filho (childNode) .
        - 'afterend'
            Após o elemento.  


# Interação com o CSS