
# Regex e Expressão Regular

- Expressão regular é uma forma de identificar padrões em um texto.
- Regex é o motor mais popular que le uma expressão regular.
- Para ver todos os comando é só pesquisar por "regex mdn"

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

# Procurando boas regex prontas

- Se vc for validar um campo comum que provavelmente muitos outros projetos tb fizeram, procure a regex e use a da comunidade, as chances de ter um bug vão ser bem menores.
- O melhor lugar é a pesquisa cair no stack over flow (forum de codigos)
