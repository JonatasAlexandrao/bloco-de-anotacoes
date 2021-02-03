
# Regex e Expressão Regular

- Expressão regular é uma forma de identificar padrões em um texto.
- Regex é o motor mais popular que le uma expressão regular.
- Para ver todos os comando é só pesquisar por "regex mdn"

Um código regex sempre estara entre `/ /`

## Criar Regex
- `const regex = /palavraDeTeste/`

## Testando se o texto contem a palavro do Regex
- Sempre vai retornar true ou false.
- regex.test('asda')
```
const resultado = regex.test(texto)
console.log("resultado: ", resultado)
```

## Verificar se o texto começa com a palavra

 - regex = /^Primeira/
```
const regex = /^Primeira/
const resultado = regex.test(texto)
console.log("resultado: ", resultado)
```

## Verifica se o texto termina com a palavra
 - regex = /Ultima$/
```
const regex = /Ultima$/
const resultado = regex.test(texto)
console.log("resultado: ", resultado)
```

- Se vc criar um regex com /^Primeira asd asdffa Ultima$/ e testar um texto que tenha a primeira palavra igual e a ultima palavra igual o resultado vai ser FALSE, pois esse regex só vai retornar true se tudo for igual da primeira palavra a ultima.

## Validando numeros

- `const regex = /[0-9]/`: verifica se é um numero entre 0 e 9.

- `const regex = /[0-9]{4}/`: indica que é um texto de 4 digitos e verifica se eles são numeros.

- `const regex = /[0-9]{4,8}/`: indica que é um texto com o minimo de 4 digitos e o maximo de 8 e verifica se eles são numeros.


## Simbolos:

- `\D`: Qualquer valor q não seja numero
- `\d`: Qualquer valor q seja numero
- `g`: global, significa q o regex é para a string toda
- `i`: insensitive, a pesquisa vai pegar strings com letra maiúsculas tb. 
- `*`: (opcionais) 0 ou n
- `+`: (obrigarório) 1 ou n
- `?`: (opcionais) 0 ou 1

- `\d{3}`: pegar 3 numeros, se fosse um \D seriam 3 não numeros
- `{1,2}`: um ou dois numeros, um intervalo
- `()`: cria um grupo, dessa forma vc pode criar uma regra mais complexa que trabalha varios pontos da string.
- `'$1'`: quando se tem um grupo vc referencia eles usando $ mais o numero do grupo assim vc pode chamar cada grupo separadamente e por a sua logia.
- `\d+`: independente de quantos numeros tiverem
- `\$`: o sifrão significa o final da string
- `\.`: o ponto é um caracter especial no regex por isso para usalo como ponto vc precisa por uma barra invertida, isso é para qualquer caracter especial.

  - Exemplos:
  ```
  value.replace(/\D/g, '') //toda entrada de valores não numero serão trocadas por 'nada', uma validação para campos de apenas numeros.

  value.replace(/(\d{3})(\d)/, '$1.$2') // quando tiver três numeros seguidos de um quarto numero ai sim vai entrar nessa condição que ira adicionar um ponto depois do terceiro numero

  value.replace(/\123$/) //só ira entrar quando o final da string tiver exatamente ...123

  value.replace(/\^123/) // só ira entrar quando o inicio da string for 123
  ```

  ## Funções Regex
    - .teste: retorna um true ou false caso exista ou não a string. `regex.test(txt)`
    - .exec `regex1.exec(texto)`
    - .match: `texto.match(regex1)`

  ## Função para remover acentos
  `texto.normalize('NFD').replace(/[\u0300-\u036f]/g, '')`






# Procurando boas regex prontas

- Se vc for validar um campo comum que provavelmente muitos outros projetos tb fizeram, procure a regex e use a da comunidade, as chances de ter um bug vão ser bem menores.
- O melhor lugar é a pesquisa cair no stack over flow (forum de codigos)
