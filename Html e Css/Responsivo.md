# Responsivo
Fazer com que a pagina encaixe tanto em telas grandes quanto pequenas.

- `breaking point`: são os pontos (os tamanhos e lugares) aonde a pagina quebra. Devem ser encontrados e tratados.

# Propriedades CSS
- `max-width e max-height`: escolhe um tamanho máximo para um elemento que nunca deve ser ultrapassado.
- `min-width e min-height`: escolhe um tamanho mínimo para um elemento que nunca deve ser reduzido.

- `@media`: midia queries, é um teste q vai verificar se a condição que for passada é verdadeira, se for ele faz o que tem dentro. No caso a baixo caso a tela seja de no máximo 1310px ele vai retirar a margin direita.
```
@media (max-width:1310px) {
  .photo-product{ 
    margin-right: 0;
  }
}
``` 

