# JSON - JavaScript Object Notation


## Criando um objeto:
```
const languageC = {
    nameClass: "-front",
    src: "img/icon-c.png" ,
    alt: "Ícone de um livro de C++"
}
```
- Para acessar as informações do objeto basta passar o nome.propriedade. Ex.: `languageC.src`.

- Você pode criar um JSON diretamente dentro do parametro function sem a necessidade de criar uma variavel pra ele e depois passar essa variavel no parametro da function.
```
createMemoryCard({
    nameClass: "-front",
    src: "img/icon-c.png" ,
    alt: "Ícone de um livro de C++"
})

As chaves indicam que é um JSON
```

## Object destructuring
- Extrair as propriedades de um objeto e cria variaveis para armazenalas com o nome de suas chaves. Você pode escolher quais propriedades serão extraídas.
```
const { src, alt, nameClass} = card
```
- Você pode ainda usar o object destructuring direto no parametro que está recebendo um JSON
```
const createMemoryCard = ({ src, alt, nameClass}) => {
    ...
}
```