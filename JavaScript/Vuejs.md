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

- Pronto, para rodar o projeto:
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
São propriedades usasdas no HTML que vem do Vue.

- v-model
- v-if -> usa uma condição if como propriedade HTML para verificar se o elemento vai aparecer, se ele não for ele "destroi" o elemento e dessa forma ele some até da arvore do Doom (caso o valor altere em execução ele reconstroi para aparecer).
- v-else -> deve ser usado logo abaixo ao v-if
- v-else-if
- v-show -> usa uma condição igual ao if mas para sumir com o elemento ele usa um display: none. Não existe uma opção para o else.
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