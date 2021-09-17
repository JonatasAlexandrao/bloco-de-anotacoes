
Sass é um pré-processador e framework para CSS.

# Seletores
Com o sass vc pode aninhar seletores.
Usando o &. 
É possível aninhar atributos tb.
```
// ---- CSS ----
a { color: #fff; }
a:hover { color: #000; }
// ---- Sass ----
a { 
  color: #fff;

  font: {
    family: Arial;
    size:14px
  }

  &:hover { color: #000; } 
}
```

# Variáveis
  Para declarar a variavel: `$NomeVar`
  Vc pode usar uma variavel dentro dos atributos de outra variavel:
  `$NomeVar: solid, 1px $cor`

# Extend
Vc pode criar uma classe e extender ela para outras classes evitando a necessidade de reescrever código.
```
.msg {
  border: 1px solid;
  padding: 10px;
  text-align: center;
}

.msg-error {
  @extend .msg;
  color: red;
}
```

# Mixins
O mixins é como se fosse uma rotina nas linguagens de programação, vc passa parametros e ele executa algumas funções mas não tem nem um retorno.
Vc pode passar um valor padrão para o parametro `$radius: 5px`, dessa forma caso não seja passado um valor ele ira usar o padrão.
O mixins NÃO DEVE SER usado para blocos de código estáticos, que não precisam receber nem uma variável! Para isso usar o Placeholder

```
@mixin border-radius($radius: 5px) {
  webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  -ms-border-radius: $radius;
  border-radius: $radius;
}

.box{
  @include border-radius(10px);
}

```
O mixins ainda tem a opção de usar um @content, funciona como o slot do vue.js, os atributos que vc adicionar no include iram substituir o @content.
```
@mixin desktop {
  @media (min-width: 500px)
    @content
}


body {
  @include desktop {
    padding 10px;
  }
}


```

# Funções
O Sass tem algumas funções já prontas que podem ser chamadas, exemplo:
  - lighten($color, 50%), clareia a cor conforme a porcentagem passada.
  - darken($color, 50%), escurece a cor conforme a porcentagem passada.
  - transparentize($color, .5), adiciona transparência a cor, valor entre 0 e 1. 

Vc pode criar as suas próprias funções, uma função precisa ter um retorno.

```
@function calc-fluid($target, $container) {
  @return ($target / $container) / 100%;
}

.divUm {
  width: calc-fluid(500, 1000);
}

```

# Placeholder
Usado para aproveitar um bloco de estilos estático, valores sem variáveis.
Sua vantagem é q quando ele converter para css ele irá agrupar os códigos repetidos.
```
%center {
  display: block;
  margin 0 auto;
}

.divUm {
  @extend %center;
}

```

# Condicionais (If / else / else if)

Condicionais iguais a linguagens de programação.
```
$template: dark;

header{
  @if $template: == dark {
    color: #fff;
  }
  @else if $template: == light {
    color: #000;
  }
  @else {
    color: #555;
  }
}

```

# Iteração (for)

# @media
Usando a @media com o sass vc pode aninhar ela dentro do seletor, em vez de ter que chama-lo novamente.
```
.sidebar {
  width: 30%;
  @media min-width: 200px {
    width: 50%
  }
}
```

# @import
Funciona igual ao css.
Com Sass o padrão é criar um arquivo que ira chamar todos os outros importando eles, para que depois ele possa compilar para css.
É comum os arquivos Sass terem um _ na frente (_base.scss), isso indica que esse arquivo só deve ser compilado quando for importado.
