# <b>JavaScript</b>

# Variaveis
- `const`: é um tipo de variavel q tem seu valor fixo, não pode ser alterado.

- `let`: é uma variavel local, ela só é visivel dentro do escopo que ela foi criada.

- <b>Array(listas)</b>
    - `$stars[0]`: pega o primeiro item da lista, dentro dos colchetes vai a posição na lista.
    - `$stars.length-1`: retorna a quantidade de itens que tem na lista, -1 pq a lista sempre começa do zero. Pode ser usado para pegar o ultimo item tb.

# Propriedades
- `console.log("")`: para aparecer uma mensagem no console do navegador.
- `elemento.textContent`: serve para pegar ou mudar o texto de um elemento.


# Seletores
- `window.document.querySelector(".-heat")`: o window é o navegador, o document o html, o querySelector é a tag selecionada e dentro dos parênteses vai ter o nome da class. 

- `const heart = window.document.querySelector(".-heart")` : na maioria das vezes um elemento vai ser guardado dento de uma variavel para ser usado no js.

- `elemento.classList`: lida com as classes do elemento, podendo adicionar, remover ou alterá-las.
    - `.classList.add("novaClass")`: adiciona classe nova ao elemento.
    - `.classList.remove("novaClass")`: remove a classe do elemento.
    - `.classList.contains("novaClass")`: verifica se contem a classe naquele elemento e retorna um true ou false. Bom para usar em um if de verificação.
    - `.classList.toggle("novaClass")`: o toggle faz a verificação se existe a classe passada, caso exista ele a remove, se não existir ele a adiciona. Facilitando essa ação de adicionar e remover a classe.

# Eventos
- addEventListener: adicionar um ouvinte de evento, significa que vc quer q o js fique de olho e avise quando for usado o evento que vc escolheu daquele elemento.
    - Click: Evento de click, o codigo só será lido quando o ususario clicar naquele elemento.
    ```
    $heart.addEventListener("click", handleClick);
    ``` 


# Funções
- Uma função é um bloco de código que vc quer que seja lido depois ou varias vezes em locais diferentes. a palavra chave é `function`, depois vc dá um nome a ela e dentro dos parenteses vc passa os parametros.
```
function handleClick() {
    console.log("ae");
}
```
- Quando vc quer colocar uma função para ela ser executada apenas quando o evento for ativado vc passa ela sem os parenteses. Os parenteses indicam "executar a função" para o navegador.
´´´
$heart.addEventListener("click", handleClick);
´´´

# Boas Práticas

- `$heart`: Toda variavel q é atribuida para um seletor html, um elemento html deve ter um "$" no inicio.

- <b>Concatenando strings:</b>
    Tudo que estiver dentro das crases é considerado string, quando vc usar `${}` o que estiver dentro será considerado codigo.
```
variavel = `Carrinho(${++valorInicial})`
```