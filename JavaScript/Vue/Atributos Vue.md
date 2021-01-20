



## Props - passar dados do pai para filho direto
É uma maneira de vc passar dados para dentro de um componente.
`<Cliente descricao="asdasd" num="123"></Cliente>`
Dentro do script do componente vc cria um objeto chamado props e dentro dele vc define os atributos que quer receber.
```
props: {
  descricao: String,
  num: Number
}
```
Uma vantagem do props é poder passar cada propriedade como objeto e assim poder setar seu tipo, se ela é obrigatória, valor padrão para inicia-la...
```
props: {
  nome: {
    type: String,
    required: true,
    default: 'Anônimo'
  }
}

```


## Watch - Monitorar Mudanças 
No watch diferente das outras propriedades vc deve escolher alguma que já esteja sendo usada para que ela monitore. Ele sempre ira retornar primeiro o valor novo e dpois o valor antigo.
`watch: {
      contador(novo, antigo) {
}`


## Methods - Criar eventos
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
O filtro é uma função que recebe um valor, transforma esse valor e retorna um novo valor transformado.

```
<p>Email: {{cliente.email | filtroAqui}}</p>

...

filters: {
  filtroAqui: function(value){
    return value.toUpperCase();
  }
}


filters: {
  cpf(valor) {
    const arr = valor.split('')
    arr.splice(3, 0, '.')
    arr.splice(7, 0, '.')
    arr.splice(11, 0, '-')
    return arr.join('')
  }
}


// DECLARANDO UM FILTER DE FORMA GLOBAL
Vue.filter('inverter', function(valor) {
  return valor.split('').reverse().join('')
})

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
## Metodos de ciclo de vida
  https://dev.to/alexandrefreire/diagrama-do-ciclo-de-vida-vue-js-16dn

### created
Vai rodar no momento da criação do vue.
```
created() {
  console.log('inicio')
}
```