
# Exemplo

```
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)
const store = new Vuex.Store({
  state: {
    produtos: [
      {name: 'pao', valor: 20.00},
      {name: 'sacola', valor: 1.00},
      {name: 'doce', valor: 15.00}
    ],
    activeListClient: true
  },
  
  getters: {
    somando(state) {
      let soma = 0
      state.produtos.map(p => soma += p.valor)
      return soma
    },
    activeClient({ activeListClient }) { 
      return activeListClient = !activeListClient
    }
  },

  //seters
  mutations: {
    adicionarProduto(state, payload) {
      state.produtos.push(payload)
    },
    activeClientMutations(state) {
      state.activeListClient.push(!state.activeListClient)
    }
  },
  actions: {
    adicionarProduto(context, payload) {
      setTimeout(() => {
        context.commit('adicionarProduto', payload)
      }, 1000)
    }
  }

})
export default store
---------------------------------------------------------
computed: {
    activeList() {
      return this.$store.state.activeListClient
    },
}

//get
this.$store.getters.somando

//mutations
this.$store.commit('activeListClient', value)

//actions
this.$store.dispatch('activeListClient', action)

```

# State
  Tipo o data() do vue, guarda o estado das variáveis.

# Getters
  Responsavel por apresentar o valor da State, podendo formatalo ou algo assim e depois entregar seu resultado sem altera a State.

# Mutations
  São funções responsaveis por alterar o valores da State.

# Actions
  As action tem a função de chamar uma ou mais mutations, é aqui onde vc vai por regras e condiçoes, a mutation só deve alterar o state e nada mais.