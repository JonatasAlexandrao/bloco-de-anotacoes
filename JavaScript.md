
# API do DOM

São comandos, mas não são do javaScript.
Serve para acessar os recursos do browser
API é o meio do caminho aonde, nesse caso fica entre o javaScript e o navegador.

# IIFE - Immediately Invoked Function Expression

- Usada para envolver todo o codigo js para não deixa-lo publico.
- Uma função expressa que se invoca imediatamente.
- Isolar as variaveis por escopo dos arquivos. Isso isola para ter menos efeitos colaterais, deixando global somente o que precisa ser global mesmo.
- Para fazer isso vc deve criar uma function sem nome que se invoca automaticamente quando for criada, por não ter nome ela tb não podera ser mais chamda.
```
(function(){
    ...
})()
```
# Padrão de organização usando module.
- Esse padrão consiste em criar uma `const module{}`, ela é um JSON. Agora em vez de você atribuir todas as funções com uma const diferente vc usa essa e adiciona a função no JSON. No final vc retorna somente as funções que vc quer que tenham um escopo global.
```
(function(){
    const module{}

    module.funcaoUm = () => {...}
    module.funcaoDois = () => {...}
    module.funcaoTres = () => {...}
    module.funcaoQuatro = () => {...}

    return funcaoUm: module.funcaoUm,
        funcaoTres: module.funcaoTres

})()
```

# Padrão comum para nomear functions e atributos privados
- Usasse um _ antes do nome delas. Assim sempre que vc ver um _algumaCoisa significa que esse elemento deve ser privado.


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

# False em JavaScript 
Eles vão retornar false em um if:
- Nulo é falso;
- Undefined é falso;
- String vazia ("") é falso;
- Zero (0) é falso;


obs.: se o 0 estiver como string ele vai retornar verdadeiro.




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

# Pegando a origim de um elemento
- `event`: vai retornar um JSON com todas as informações sobre o elemento.
- `event.target`: Retorna o caminho do elemento. 

- `$origin.parentNode`: retorna o caminho do pai desse elemento.

- `$origin.closest('classe-procurada')`: retorna o caminho do elemento acima na arvore que tenha a classe passada.

# Verificar se existe uma class no elemento
- `$elemento.classList.contains('classe')`: verifica se o elemento tem a classe passada e retorna true ou false.



# Interação com o CSS