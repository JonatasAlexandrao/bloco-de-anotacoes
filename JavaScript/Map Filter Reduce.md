
# Map()
 - `[1,2,3].map(fn)`
    O Objetivo dela é transformar um array e devolver um array como resultado.
    O resultado de um map vai ser sempre do mesmo tamanho do array passado.
    Ela vai fazer oq foi passado na função para cada item do array.
 - O map espera 3 parametros: uma função, o index e um array.



# Filter()

- `[1,2,3].filter(fn)`
    Retorna um array filtrado pela função que foi passada. Se essa função retornar 'true' o valor é adicionado ao novo array se o retorno for 'false' o valor é ignorado.


# Reduce()
- `[1,2,3,4,5].reduce(fn, i)`
   - A função agora terá dois parametros, o primeiro é o 'acumulador' e o segundo o 'elemento' igual o filter e o map.
   - o return do reduce pode ser qualquer coisa.