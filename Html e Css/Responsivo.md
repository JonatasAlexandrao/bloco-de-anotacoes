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

  ## Imagem respeitando container pai
  - `object-fit`: define como um objeto deve se comportar perante um elemento com dimensões definidas.
    - `fill`: preenche todo o elemento com o conteúdo da imagem, mantendo as dimensões definidas para o elemento, não a proporção da imagem
    - `contain`: preenche todo o elemento com a maior dimensão da imagem, adaptando a menor dimensão conforme a proporção origina
    - `cover`: preenche todo o elemento com a menor dimensão da imagem, adaptando a maior dimensão conforme a proporção original, ocultando o conteúdo da imagem que excede as dimensões do elemento
    - `none`: preenche o elemento com a imagem em seu tamanho original, ocultando o conteúdo que excede as dimensões do elemento
    - `scale-down`: a imagem será adaptada à sua menor versão entre os resultados de none ou contain
