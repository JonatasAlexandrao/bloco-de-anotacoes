# BOM - Browser Object Model (Modelo de Objeto do Browser)

O Bom é uma interface que define métodos para usar recursos do próprio navegador. Como mexer com a url e atualizar a pagina.
- Para chamar um recurso do BOM usasse `windows.`, mas você pode omitir a palavra que funciona do mesmo jeito.

## Alguns recursos:
- `window.location.hash`: serve para pegar o caminho da pagina ou alterar esse caminho. 
- `window.location.reload(true ou false)`: recarrega a pagina, se for passado "true" usa o cach do navegador para não precisar fazer uma requisição direta ao servidor.

# DOM - Document Object Model (Modelo de Objeto de Documento)

O dom é uma interface de programação que define métodos para acessar a arvore HTML. Com ele você pode alterar as estruturas do documento. Todo recurso que você queria usar que seja do documento como adicionar um elemento a tela, alterar um elemento ou excluir algum.

- Para chamar um recurso do DOM usasse `document.`, mas você pode omiti-lo que vai funcionar.

## Alguns recusros:
- `document.querySelector('nome-da-classe')`: pega o elemento que tenha essa classe.

- `document.createElement('nome-do-elemento')`: cria um novo elemento no documento.
