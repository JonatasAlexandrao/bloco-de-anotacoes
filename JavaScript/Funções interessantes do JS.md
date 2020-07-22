
# Convertendo String para Numero:

  ## String para Decimal
  `parseInt(num1)`

  ## String para Float
  `parseFloat(num1)`

  ## Numero para String
  `1 + ""` = "1"

# Arredondar casas decimais:
  `num = 20.339999999`
  `num.toFixed(2)`
  = 20.34

# Trocando caracteres por outros:

  ## replace()
  Troca o primeiro parametro pelo segundo.

    ```
    const n = "20,22";
    n.replace(",",".");

    resultado = "20.20"
    ```
# Separar string e guardar em array
  ## split()
  Retorna um array e guarda cada pedaço da string, cortando nos pontos do caracter passado como parametro.
  ```
  const valor = '20,33'
  const split = valor.split(',')
  const valor2 = 'texto um'
  const split2 = valor2.split(' ')

  Resultado = split[0] -> 20
              split[1] -> 33
              split2[0] -> texto
              split2[1] -> um
  ``` 
  ## substr()
  O método substr() retorna os caracteres em uma string começando na localização especificada através do número especificado de caracteres.
  ```
  var str = 'abcdefghij';
  str.substr(1, 2)  // (1, 2): bc
  str.substr(-3, 2) // (-3, 2): hi
  str.substr(-3)    // (-3): hij
  str.substr(1)     // (1): bcdefghij
  ```