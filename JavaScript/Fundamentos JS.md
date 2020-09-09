# Paradigma funcional
  É um paradigma da programação, trata o código semelhante a funções matemáticas e evita dados mutáveis, seu foco está no uso das funções.
# Função pura
  - Funções que não trazem efetito colateral, a ideia é que passado os parametros para ela o seu retorno sempre será o mesmo não importando quantas vezes ela seja usada. Para isso ela não pode usar dados de fora dela, nem contadores ou numeros de forma randomica.

# Higher-Order Function
  - Função pode retornar uma função e podem receber uma função como parametro.

# First-Class
  - Funções são valores na linguagem, elas podem ser armazenadas em variaveis.

# Imutabilidade


# Closure
- É quando uma função "lembra" do seu escopo léxico(é onde ela foi criada).
- Toda função em Js é closure.

# Currying
- É uma forma de compor uma função
```
// Forma comum
function soma(a, b, c) {
  return a + b + c
}
console.log(soma(1,2,3))

// Forma Curryning
function soma(a) {
  return function(b) {
    return function(c){
      return a + b + c
    }
  }
}
console.log(soma((1),(2),(3)))
```
- Usando currying vc pode usar varias versões parciais da mesma função. Vc poderia testar cada pedaço da função.

# Lazy Evaluation (avaliação preguiçosa, tardia)
- Ela usa os conseitos de Closure e Curryning para rodar uma partes da função somente quando todas as outras informações já estiverem prontas. Isso economisa processamento e tempo de execução. Ele vai deixar para o mais tarde possivel essa execução.

# Composições de Funções
- É quando vc passa o resultado de uma função para outra função, concatenando varias funções e interligando elas.

# Functors
wrapper (algo que envolve), container
vc passa um valor e altera o que tem dentro usando um .map
- Functors são objetos que implementam a função MAP
- Que também é um "wrapper" de um valor.
```
const nums = [1,2,3,4]
const novosNums = nums
  .map(el => el + 10)
  .map(el => el * 2)

//Resultado
[22, 24, 26, 28]
```

# FlatMap
- flat() -> ele "achata" um array. 
Ex.: [1, [2, 3]].flat() ====>>> 1, 2, 3 
- O flatMap() faz primeiro o map e depois achato com o flat e ai retorna esse valor


# Função Callback

# Função map, filter e reduce

# Promise