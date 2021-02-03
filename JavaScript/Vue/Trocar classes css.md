<div :class="{c1: ap}"> o primeiro parametro é a classe o segundo um boolean q vai indicar se deve ou não ser usada

  @click='ap = !ap'

  data: {
    ap: false
  }

  <div :class="estilo">

  computed: {
    estilo(){
      return {
        c1: this.ap
        c2: !this.ap
      }
    }
  }
  para casos mais complexos vc pode usar uma variável computada, nesse exemplo ela retorna um objeto aquele que for verdadeiro será retornado, então nessa situação ele vai ficar trocando entre c1 e c2.