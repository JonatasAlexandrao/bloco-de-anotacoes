
## Atribuir um tipo a variáveis
  Existem 3 tipos primitivos que podem ser usados para atribuição: string, number e boolean

```
  let name: string;
  let num: number;
  let teste: boolean;
```

## Limitando o que pode ser atribuído a uma variável
  É possível escolher quais tipos uma variável pode ter ou ainda os valores que podem ser atribuídos a ela.
```
  let teste = string | number
  let color = 'red' | 'green' | 'blue'
```

## Criar seu próprio tipo
  Você pode criar seu próprio tipo com as características necessárias e assim evitar repetições

```
  type Color = string | number 
  ou
  type Color = 'red' | 'green' | 'blue'
  let corDoFundo = Color
  corDoFundo = 'green'
```

## Interface
  É possível criar um objeto e escolher o tipo de cada propriedade, além de poder escolher se são obrigatórias.
  ```
    interface Dog {
      name: string,
      race: string,
      age?: number,
      color: 'black' | 'white' | 'yellow'
    }
  ```
  propriedades com um '?' são opcionais, logo se não forem usadas não terá problema.

  const dog1: Dog = {
    name: Thor,
    color: 'black'
  }

## Funções
  Em funções você pode definir os tipos dos parâmetros e da resposta

  ```
    function sun(num1: number, num2: number): number {
      return num1 + num2
    }
  ```