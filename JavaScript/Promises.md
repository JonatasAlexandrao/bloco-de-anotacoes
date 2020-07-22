# Callbacks
  - É uma função que é passada por outra
  - É uma função asincrona, ela não atrapalha o ciclo de leitoura... por exemplo essa função retorna uma string com os valores de um arquivo que vai ser lido, em vez do programa ficar esperando ele fazer isso pra continuar ele separa essa ação e continua fazendo o resto, quando o resultado vier ele chama essa função de volta.


# Promise
  - `let p = new Promise((resolve, reject) => {
    ...
  })`
  - As promises são uma promessa de retornar um valor no futuro. Ela serve para resolver o problema das situações asincronas.
  - Uma promese vai ter um retorno de resolve e outro do reject que seria um caso de erro.
  - Ele ajuda a fazer o código crescer pra baixo e não pro lado.
  - Vc pode encadear o uso do Promise:
    ```
    promise('asdf')
      .them( contents => {...console.log(1)})
      .them( contents => {...console.log(2)})
      .them( contents => {...console.log(3)})
    ```

# Async/Await
  - É um açucar sintático em cima da promise
  - Usando o await é como vc usasse uma função asincrona como sincrona. Colocando essa palavra ele vai executar aquela função e esperar o resultado para ir para a próxima.