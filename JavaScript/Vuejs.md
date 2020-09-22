# Vue.js
- é legal instalar a extenção Vetur no vsCode.

## Vue CLI
Uma ferramenta para ajudar na hora de criar o projeto de uma forma simples sem precisar ficar configurando tudo.
Terminal:
  npm install -g @vue/cli 
  vue -v (verificar se foi instalado)

## Criando projeto
- Ele necessita do node instalado antes
- No terminal: 
    vue create nomeDoProjeto
    enter

- Pronto,k para rodar o projeto:
    npm run serve

## ERRO na hora de criar um novo projeto
```
  $ sudo npm uninstall -g vue
  $ sudo npm uninstall -g vue-cli
  $ sudo npm uninstall -g @vue/cli
  $ sudo npm cache clean --force
  $ sudo npm install -g vue
  $ sudo npm install -g @vue/cli
```

## Arquivos .vue
O Vue.js usa essa extenção .vue, esse arquivo vai ser usado para criar seu componente. 
Ele é dividido em 3 tags:
  - <template></template>
  - <script></script>
  - <style></style>
Dentro da template vai o código HTML, dentro da script o JavaScript e na style o CSS. Sendo que na style podesse adicionar a propriedade scoped na tag que ira dizer que aquele código só será usado para aquele arquivo, evitando que ele afete outros componentes.

## Componentes
Para criar um componente vc cria um arquivo .vue na pasta components e adiciona o seu código separado nas 3 tags.
Para adicionar o componente dentro da pagina ou dentro de outro componente: 
```
<template>
  <Cliente/>
</template>

<script>
import Cliente from './components/Cliente'
export default {
  name: 'App',
  components: {
    Cliente
  }
}
</script>
```
## <script></script>
Dentro da tag script teremos um `export default {}` tudo oque estiver dentro vai ser exportado para fora.
Dentro dela temos algumas propriedades:
  - name:
  - components: { aqui é aonde vc chama os componentes que vc vai adicionar }
  - data(){ return { nome:"aasdd", numero:"4564" são informações do componente que vc pode acessar depois } }

## Data binding
A primeira forma é usar {{ nome }} ou :value="nome".
  - {{}} permite que vc use codigo js no HTML
  - : antes de uma propriedade HTML permi vc usar uma variável no seu valor.
As duas formas acima são somente leitura.

  ### v-model="variavel"
  Essa propriedade dentro da tag HTML cria uma ligação aonde sempre que essa variavel mudar o valor no HTML será atualizado reativamente.

## Props
É uma maneira de vc passar dados para dentro de um componente.
`<Cliente descricao="asdasd" num="123"></Cliente>`
Dentro do script do componente vc cria um objeto chamado props e dentro dele vc define os atributos que quer receber.
```
props: {
  descricao: String,
  num: Number
}
```
## Diretivas
São codigos usados nas propriedades do HTML para que elas consigam entender uma função ou codigo js.

- v-model -> é uma diretiva q altera tanto o visual na tela quanto a variavel por traz, ele link as duas coisas usando o two-way-binding, é o uso de duas diretivas juntas.
`<input type="text" v-bind:value="titulo"
    v-on:input="titulo = $event.target.value">`
ficando assim:
`<input type="text" v-model="titulo">`
  

- v-on -> usar ela em propriedades de interação q vc vai passar um evento como Click, Mouse movi. Por padrão sempre que é chamado um evento do browser ele será passado como parametro para seu evento, vc pode usar um 'teste(event)' e pegar esse evento passado para usar usas infomações.
  - Caso vc queira pegar o event e passar um parametro seu junto vc precisa usar uma palavra reservada chamada $event
  `teste(num, $event)`
Ele atualiza do HTML para o javaScript
Sintaxe reduzida: v-on:click="titulo" --> @click="titulo" 

- v-bind -> muito usada, ela vai fazer a associação da propriedade com a variavel passada, podendo assim passar valores por ela e se alterados mudaram automaticamente.
`<input type="text" v-bind:value="nome">`
Ele atualiza do javaScript para o HTML
Sintaxe reduzida: v-bind:value="contador" --> :value="contador"

- v-html -> serve para acionar codigo html como propriedade. 
```
<p v-html="linkhtml"></p>

linkhtml: '<a href="http://google.com.br">Google</a>'
```

- v-once -> vc usa dentro de uma tag html como uma propriedade e isso vai garantir que ela seja alterada apenas a primeira vez.Ex.: `<p v-once>{{ titulo }}</p>`

- v-if -> usa uma condição if como propriedade HTML para verificar se o elemento vai aparecer, se ele não for ele "destroi" o elemento e dessa forma ele some até da arvore do Doom (caso o valor altere em execução ele reconstroi para aparecer).

*** Caso vc queira usar um v-if em um grupo de codigo em vez de envolve-lo com uma tag div vc pode usar a tag <template> essa tag vai funcionar igual a div com a diferença de q quando o elemento for renderizado na tela ela some deixando os itens juntos mas sem nem uma tag agrupando.

- v-else -> deve ser usado logo abaixo ao v-if

- v-else-if

- v-show -> usa uma condição igual ao if mas para sumir com o elemento ele usa um display: none. Não existe uma opção para o else. Ele é bom para esconder algum conteúdo q vc vai reutilizar, um menu por exemplo, mas lembre-se o codigo está lá e pode ser acessado pelo código se for alguma coisa de segurança é melhor usar o v-if.

- v-for -> ele vai replicar o código HTML que ficar dentro da estrutura para cada elemento que tiver no objeto passado pra ele.
  ```
  <div v-for="cliente in clientes" :key="cliente.id">
    <Cliente :cliente="cliente"/>
  </div>
  ```   
  lá no data() tem que ter o retorno de todos os cliente é obrigatório ter uma key diferente para cada um deles.
  Essa estrutura for pode devolver um índece tb
  ```
  <div v-for="(cliente, index) in clientes" :key="cliente.id">
    <Cliente :cliente="cliente"/>
    <p>{{ index }}</p>
  </div>
  ```

## Monitorar Mudanças ( watch )
No watch diferente das outras propriedades vc deve escolher alguma que já esteja sendo usada para que ela monitore. Ele sempre ira retornar primeiro o valor novo e dpois o valor antigo.
`watch: {
      contador(novo, antigo) {
}`


## Classes condicionais (troca de classe em execução)

```
<div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">

// quando isPremium for false ele vai add na class o 'cliente', quando isPremium for verdadeiro ele add a class 'cliente-premium'


<script>
export default {
  data(){
    return {
      isPremium: false
    }
  }
}
</script>
```

## Eventos
Para adicionar um evento dentro da tag HTML do elemento basta digitar `@` e o nome do evento.
Os eventos sempre retornam algum dado.
Vc pode criar metodos tb.
  ```
  <button @click="">

  ...

  <script>
    export default {
      methods: {
        mudarCor: function {
          console.log('mudou');
        }
      }
    }
  </script>
  ```
  - $event: Esse retorno do evento peve ser usado com uma palavra chave caso vc esteja passando parametros pernsonalizados.
  `teste(num, $event)`
  - O efeito de um evento normamelmente ira propagar para os componentes filhos.

    ### Modificadores de eventos
    Com eles vc consegue modificar o comportamento padrão do evento.
    - .stop: `v-on:mousemove.stop=""` dentro desse componente o evento não vai ser propagado.
    - .prevent: `<a v-on:click.prevent=""  href="http://google.com">Google</a>`
    Ele impede o comportamento padrão, nesse caso o link não ira acessar o google.
    #### Eventos de teclado
    Usando por exemplo o v-on:keyup vc pode passar o modificador sendo ele uma tecla do teclado e assim disparar um evento quando ela é precionada, existe um modificador para cada tecla.
    `v-on:keyup.enter="exibirAlerta"`
    Vc ainda pode encadear os eventos, dessa forma só será acionado o evento quando todas as teclas passadas forem precionadas.
    `v-on:keyup.enter.alt="exibirAlerta"`



  ## Filters:
  Um filtro sempre recebe um valor e tem que retornar algo.
  Esse filtro serve para que vc altere a forma de exibição de uma variavel passada, como por exemplo pegar um email escrito normal mas mostrar ele escrito com todas as letras maiusculas.
  Isso não altera os dados da variavel.

  ```
  <p>Email: {{cliente.email | filtroAqui}}</p>

  ...

  filters: {
    filtroAqui: function(value){
      return value.toUpperCase();
    }
  }
  ```

  ## Computed properties
  São dados dinamicos
  Por padrão uma variavel no vue só recebe um valor.
  Elas sempre precisa retornar um valor.
  Ela é usada como uma variavel comum mas ela na verdade é uma função q vai retornar um valor.


  ```
  computed: {
    idEspecial: function() {
      return (this.cliente.email + this.cliente.id)
    }
  }
  ```

 

  ## Bibliotecas

  ### loadsh
  Uma biblioteca para ordenar uma lista da forma que quiser. 
  terminal: npm i --save lodash
  Dentro da tag script do seu componente:
  `import _ from 'lodash';`