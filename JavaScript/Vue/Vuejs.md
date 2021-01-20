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


### Passar dados de filho para o pai
Usando uma função de callback, no pai vc cria essa função com aquilo q vc quer que seja feito lá no filho e passa ela dentro da tag filho.
```
<AppUsuarioInfo  :reiniciarFn="reiniciarNome"/>
```
No filho vc cria uma props do tipo Function q será a função passada pelo pai, depois vc pode chama-la de dentro do filho.
```
<button @click="reiniciarFn()">Reiniciar Nome (Callback)</button>
...
props: {
   reiniciarFn: Function
}
```

### Passar dados entre irmãos


## Keep-alive
Essa tag serve para vc impedir que um componente seja destruido quando ele for trocado ou algo assim. Dessa forma ele mantem o mesmo estado, exemplo: uma lista de imagens onde vc troca elas em um botão de seguinte, vc usa outro botão q apaga essa imagem e troca para um texto quando vc voltar para a imagem ela tera retornado a primeira e não na ultima q vc olhou. Para usar essa tag basta por dentro dela o elemento que deve ser mantido.
```
<keep-alive>
  <component />
</keep-alive>
```

## Diretivas
São codigos usados nas propriedades do HTML para que elas consigam entender uma função ou codigo js.

  ### v-model="variavel"
  Essa propriedade dentro da tag HTML cria uma ligação aonde sempre que essa variavel mudar o valor no HTML será atualizado reativamente e sempre que o valor da variavel mudar internamente o elemento ira mudar tb. Isso se chama two-way data binding seria como uma via de mão dupla.
  - v-model -> é uma diretiva q altera tanto o visual na tela quanto a variavel por traz, ele link as duas coisas usando o two-way-binding, é o uso de duas diretivas juntas.
  ```
  <input type="text" v-bind:value="titulo"
    v-on:input="titulo = $event.target.value">
  ficando assim:
  <input type="text" v-model="titulo">
  ```
  #### v-model.laze="variavel"
  O lazy atraza a atulaização da variavel e dos elementos vinculados para quando o input, por exemplo, perder o foco.
  #### v-model.trim="variavel"
  O trim remove os espaços em branco.
  #### v-model.number="variavel"
  O number ira retornar um valor do tipo numerico, se um input estiver com o type="number" mesmo ele só permitindo q o usuari digite numeros o seu retorno será uma string, usando esse v-model.number vc resolve isso.

  ### v-on 
  -> usar ela em propriedades de interação q vc vai passar um evento como Click, Mouse movi. Por padrão sempre que é chamado um evento do browser ele será passado como parametro para seu evento, vc pode usar um 'teste(event)' e pegar esse evento passado para usar usas infomações.
  - Caso vc queira pegar o event e passar um parametro seu junto vc precisa usar uma palavra reservada chamada $event
  `teste(num, $event)`
  Ele atualiza do HTML para o javaScript
  Sintaxe reduzida: v-on:click="titulo" --> @click="titulo" 

  ### v-bind 
  -> muito usada, ela vai fazer a associação da propriedade com a variavel passada, podendo assim passar valores por ela e se alterados mudaram automaticamente.
  `<input type="text" v-bind:value="nome">`
  Ele atualiza do javaScript para o HTML
  Sintaxe reduzida: v-bind:value="contador" --> :value="contador"

  ### v-text
    -> Serve para injetar um texto dentro da tag.
    ```<p v-text="'Usando diretiva v-text'"></p>```
    
  ### v-html 
  -> serve para acionar codigo html como propriedade.
  Muito perigoso para sofrer ataques. 
  ```
  <p v-html="linkhtml"></p>

  linkhtml: '<a href="http://google.com.br">Google</a>'
  ```

  ### v-once 
  -> vc usa dentro de uma tag html como uma propriedade e isso vai garantir que ela seja alterada apenas a primeira vez.Ex.: `<p v-once>{{ titulo }}</p>`

  ### v-if 
  -> usa uma condição if como propriedade HTML para verificar se o elemento vai aparecer, se ele não for ele "destroi" o elemento e dessa forma ele some até da arvore do Doom (caso o valor altere em execução ele reconstroi para aparecer).

  *** Caso vc queira usar um v-if em um grupo de codigo em vez de envolve-lo com uma tag div vc pode usar a tag <template> essa tag vai funcionar igual a div com a diferença de q quando o elemento for renderizado na tela ela some deixando os itens juntos mas sem nem uma tag agrupando.

  ### v-else 
  -> deve ser usado logo abaixo ao v-if

  ### v-else-if

  ### v-show 
  -> usa uma condição igual ao if mas para sumir com o elemento ele usa um display: none. Não existe uma opção para o else. Ele é bom para esconder algum conteúdo q vc vai reutilizar, um menu por exemplo, mas lembre-se o codigo está lá e pode ser acessado pelo código se for alguma coisa de segurança é melhor usar o v-if.

  ### v-for 
  -> ele vai replicar o código HTML que ficar dentro da estrutura para cada elemento que tiver no objeto passado pra ele.
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




  

## Ref
é uma propriedade do vue que serve para vc referenciar um elemento do HTML.

## Style scoped
`<style scoped></style>`
Faz com que o código css digitado dentro só afete os elementos desse componente, garantindo assim q não terão efeitos colaterais em outros elementos de outros lugares. O escopo alcança até os filhos direto.

## Caminho Global
Quando vc referencia um local de arquivo em um import por exemplo: `import elemento from './components/elemento.vue'` vc está usando o caminho relativo. Se vc mudar o componente pai de lugar vc tera q alterar todos os imports. 
O caminho Global sempre inicia da pasta src e assim vc não precisa mais ficar trocando os imports.
`import elemento from '@/components/elemento.vue'` 

## Nomenclatura de arquivos


## Bibliotecas

### loadsh
Uma biblioteca para ordenar uma lista da forma que quiser. 
terminal: npm i --save lodash
Dentro da tag script do seu componente:
`import _ from 'lodash';`