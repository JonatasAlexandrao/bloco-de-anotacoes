
Para trabalhar com rotas no Vue.js podemos usar o vue-router.


# Configurando vue-router
- instalando o vue-router instalado 
  - npm install vue-router
- criar um arquivo router.js
- importar nele o Vue, o Router e os paginas (componentes)
  - ```
    import Vue from 'vue'
    import Router from 'vue-router'
    ...
    ```
- dentro do array routes vai ter varios objetos onde vc coloca o caminho do componente e o nome do arquivo dele.
  ```
  Vue.use(Router)

  export default new Router({
    mode: 'history', //ou// mode: 'hash',
    routes: [{
      path: '/',
      component: Inicio
      }, {
        path: '/usuario',
        component: Usuario
      },
    ] 
  })
  ```
- no arquivo main.js importar o router.js e registrar dentro do new Vue
  - ```
    import router from './router'

    new Vue({
      router,
      render: h => h(App),
    }).$mount('#app')
    ```
- No arquivo App.js dentro da div app vc deve adicionar o componente global router-view, será ai que os componetes(paginas) serão adicionados pelo vue-routes
  - `<router-view />`
  
# Modos de Navigação
## Hash
Na navigação por hash ele vai adicionar a url base um /#/. Desse modo o servidor vai fazer a requisição sempre para a raiz, de lá o index.html chama o app.js que chama o Vue e ai sim ele se encarega do parte a direita da url depois do hash. 



## History
Nesse modo não a o # na url e as requisiçoes no servidor são feitas direto no endereço passado. Porem para usar esse modo vc precisa configurar seu servidor para isso.

https://router.vuejs.org/guide/essentials/history-mode.html#example-server-configurations


# Router link
O router link é um componente global, que irá subistituir a tag <a></a>(link). Dessa forma a pagina não será atualizada sempre que for clicado em um link.
  - <router-link to="/">Início</router-link>

## Trocando a tag que será gerada
Caso vc queira que esse link esteja envolvido por uma tag, vc pode fazer isso usando a propriedade tag="nomeDaTag":
  - ```
    <ul>
      <router-link to="/" tag="li"><a>Início</a></router-link>
      <router-link to="/usuario" tag="li"><a>Usuário</a></router-link>
    </ul>
    ```
    OU envolvendo pela tag mesmo:
    ```
    <ul>
      <li>
        <router-link to="/" tag="li"><a>Início</a></router-link>
      </li>
      <li>
        <router-link to="/usuario" tag="li"><a>Usuário</a></router-link>
      </li>
    </ul>
    ```
## active-class
Essa propriedade serve para adicionar uma classe css quando vc entiver no caminho do link
- `<router-link to="/" tag="li" active-class="active" exact><a>Início</a></router-link>`

## exact
Essa propreidade serve para informar que o link deve ser exatamente igual ao passado na propriedade to. Em alguns casos como o caminho raiz ('/') os proximos caminhos irão começar por /alguma coisa, sem o exact esse link vai estar ativo tb pq existe / no caminho.

# Pegando parametros a parter da rota
Criar um props com o nome da parametro passado pela rota e no arquivo router.js adicionar um props: true.

```
props: ['id']

ARQUIVO ROUTER.JS
export default new Router({
  mode: 'history',
  routes: [{
      path: '/usuario/:id',
      component: Usuario,
      props: true
    },
  ] 
})

```

# Nomeando rotas
Vc pode dar um nome para uma rota para facilitar a chamada dela. Pra isso basta usar a propriedade name.
```
 path: ':id/editar', component: UsuarioEditar, props: true, name: 'editarUsuario' }


 <router-link :to="{ name: 'editarUsuario', params: { id } }">
```

# Tratar rotas inexistentes
Para fazer qualquer rota não registrada ser redirecionada.
```
{
  path: '*',
  redirect: '/'
}
```

# Interceptar navegação para um componente

  ## Intercptar antes da entrada
  `router.beforeEach((to, from , next)`
  Forma global, vai intercptar todas as rotas:
  ```
  router.beforeEach((to, from , next) => {
    console.log('antes das rotas -> global')
    next()
  })
  ```
  Os parametros são para onde(to), de onde (from) e o caminho final (next) sem ele a navegação não continua. 

  ## Intercptar uma rota expecifica
  `beforeEnter: (to, from, next)`
  Dessa vez ele intercepta antes de entrar no componente UsuarioDetalhe e como está sem o next vai impedir que entre.
  ```
  { path: ':id', component: UsuarioDetalhe, props: true, beforeEnter: (to, from, next) => { console.log('antes da rota -> usuário detalhe') } },
  ```
  ## Intercptar uma rota expecifica de dentro do componente
  `beforeRouterEnter(to, from, next)`
  ```
  export default {

    props: ['id'],

    beforeRouterEnter(to, from, next) {
      console.log('dentro do componente -> usuário detalhe')
      const autenticado = true
      autenticado ? next() : next(false)
    }
  }
  ```

# Interceptar saida de um componente
`beforeRouteLeave(to, from, next)`
```
export default {
  props: ['id'],
  data() {
    return {
      confirmou: false
    }
  },
  beforeRouteLeave(to, from, next) {
    if(this.confirmou) {
      next()
    }
    else {
      if(confirm('Tem certeza?')){
        next()
      }
      else{
        next(false)
      }
    }
  }
}
```
# Carregar tardiamente componentes
No caso de uma aplicação muito grande, carregar todos os componentes na hora que usario entrar na aplicação pode ser um problema, para resolver isso vc pode fazer com que eles carreguem apenas no momento q forem ser usados.
Em vez de importar o componente normalmente vc importa eles para dentro de uma variavel usando uma array function.
  `const UsuarioDetalhe = () => import('./components/usuario/UsuarioDetalhe')`
Vc ainda pode colocar um comentario para que alguns componentes carreguem juntos.
```
const Usuario = () => import(/* weppackChunkName: "usuario" */'./components/usuario/Usuario')
const UsuarioLista = () => import(/* weppackChunkName: "usuario" */'./components/usuario/UsuarioLista')
```