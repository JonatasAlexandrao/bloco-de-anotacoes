# Display:

# `display: inline`

```
1. Deixa elementos na mesma linha. 
2. As propriedade width e heigth não funcionam em display inline. Seu tamanho e altura são definidos pelo conteúdo que eles contém.
3. Ganham um comportamento de uma palavra. 
```

# `display: block`

 ```
1. O elemento passa a ocupar a linha toda, dessa forma não podendo ter outros elementos ao lado.
2. Permite definir width e height.
3. A maioria dos elementos vem por padrão com o display: block.
```

# `display: inline-block`

 ```
1. Permite definir largura e altura (essa é o único comportamento que é herdado do display:block).
2. Permite um elemento ao lado do outro (igual ao display:inline).
3. Ele também herda o comportamento de uma palavra (igual ao display:inline, por isso o espaço entre os elementos)
4. Por se comportarem como palavras podem ser afetadas pelo text-align.
5. Seu for usado o justify no text-align, para separar os elemento pro igual na tela, lembrar q ele não justifica a ultima linha. Para resolver isso deve criar um :after no css q vai adicionar um texto na tela, ai vc faz ele ficar na ultima linha sozinho e o deixa sem conteudo.

```

-------------------------
-------------------------

# FLOAT

- Quando se usa essa propriedade criasse um novo contexto, como se fosse uma camada a frente da normal. O elemento passa a flutuar por cima.
- Se tivermos um <img> ou um display:inline ou um display:inline-block logo em seguida de um elemento com float, esse elemento vai se encaixar ao lado daqueles q estão flutuando. Se não couber ele fica logo abaixo.


 `overflow: hidden`: tem o poder de esconder qualquer elemento filho que ultrapasse o tamanho do pai. Quando o pai não tem altura e largura definidas ele considera as dos filhos, mesmo q estejam em outro contexto.


`clear`: é usada para limpar o contexto caso tenho um elemento flutuando ao lado esquerdo(left), direito(right) ou ambos(both).
