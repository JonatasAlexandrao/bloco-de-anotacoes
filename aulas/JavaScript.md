# <b>JavaScript</b>

# Seletores

- `window.document.querySelector(".-heat")`: o window é o navegador, o document o html, o querySelector é a tag selecionada e dentro dos parênteses vai ter o nome da class. 

- `const heart = window.document.querySelector(".-heart")` : na maioria das vezes um elemento vai ser guardado dento de uma variavel para ser usado no js.

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