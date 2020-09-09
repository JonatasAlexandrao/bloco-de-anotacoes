//Olhar depois
destructuring array js `[...asdad]`
react-slick.
custom hooks

### Caso vc baixe um projeto do git vc pode instalar suas dependencias usando o comando `npm install`

# SPA - Single page aplication
  - são paginas que não atualizando e fazem requisição todo o momento que é clica em um link / botão. Um comportamento de aplicativo onde as coisas se alteram na pagina aparecem novos elementos e são fechados outros tudo sem atualizar essa pagina.

# react-router-dom
  - Documentação: https://reactrouter.com/web/guides/quick-start
  - npm install react-router-dom
  - `import { BrowserRouter, Switch, Route } from 'react-router-dom'`
  - Para usalo agente vai no index.js e remove a tag `<React.StrictMode>` pq agora agente vai usar o BrowserRouter para involver nossa aplicação.
    - O Switch será o responsavel de verificar qual rota foi escolhida como se fosse um if
    - O Route é como vc vai declarar cada pagina.
    - `exact`: vc adiciona no Route para que ele só entre na pagina que for exatamente igual ao path passado, se não no caso do path='/' ele vai renderizar sempre essa pagina pois todos os outros path começam com / logo ele já acredita que achou o que queria.
    - Criando a ultima Route sem um path, isso diz que caso ele não tenha entrado em nem uma route antem então ele vai entrar nessa. Serve para links que não existem, uma pagina padrao 404.
  ```
  ReactDom.render(
    <BrowserRouter>
      <Switch>
        <Route path='/' component={App} exact />
        <Route path='/cadastro/video' component={CadastroVideo} />
        <Route component={erro404}>

      </Switch>

    </BrowserRouter>,
    document.getElementById('root')
  );
  ```
  ## Link
  - `import { Link } from 'react-router-dom';`
  - Para usar no lugar da tag `a`, isso serve para alterar o comportamento do link para que ele não recarregue mais a pagina e mesmo assim troque tornando assim uma SPA
    - O `href` se torna `to`
  ```
  //Antes
    <a href='/'>...</a>
  //Depois
    <Link to='/'>...</Link>
  ```

# react-slick
  - Serve para fazer um carrossel
  - npm install react-slick 
  - `import styled from 'styled-components`
  - tem dois arquivos de css pra carregar no index.html
  

# styled-components
  - npm install styled-components
  - para usar no arquivo deve se importar:
    `import styled from "styled-components;`
  - é bom instalar a extenção para o vsCode ela vai fazer vc conseguir escrever esse CSS como se estivesse em um arquivo .css com coloração e ajuda.

  - O styled-components serve para facilitar a forma de escrever CSS dentro de um arquivo JS. Vc cria um elemento e atribui a ele o styled.tagHTML e depois entre crases passa o código css.
    Ex: 
    ```
    const Button = styled.a`
    color: var(--white);
    border: 1px solid var(--white);
    &:focus {
    opacity: .5;
    }
    `;
    ```

# Instalar ESLint
  Para manter um padrão no projeto, ele vai mostrar erros nas linhas que estiverem usando um padrão não recomendado.
    - npx eslint --init
    - To check syntax, find problems, and enforce code style
    - javascript modules (import;export)
    - framework usado
    - se está sendo usado typescript
    - Browser
    - use a popular style guide
    - Airbnb
    - extensão que ele vai guardar essas configurações escolhidas
    - yes

  - pode ser que de conflito de versão do eslint quando vc tentar rodar o projeto. Vc pega a versçao q ele passa no erro em verde e cola no lugar da versão que está no arquivo package.json em devDependecies
  - ai vc roda npm install pra ele baixar as coisas dessa dependencia.

  - Depois de instalado ctrl + p >eslint:enable
  para ativar o estlint

  - Um comando para corrigir os erros mais simples é
  ctrl + p >eslint: fix auto-fixable...

  - ** Caso de erro de LF / CRLF é só trocar no canto inferior direito do vsCode.

# Instalando prop-types
  Uma forma de por tipos meio que apenas semanticamente.
  - npm install prop-types

  para usar importe a biblioteca no arquivo
    - `import PropTypes from 'prop-types'`
    - ```
    Componente.defaultProps = {
      exemplo2: 'text',
      exemplo3: '',
      exemplo4: 0,
      exemplo5: () => {},
    }
    Componente.propTypes = {
      exemplo: PropTypes.string.isRequired, // campo obrigatório
      exemplo2:  PropTypes.string, // não obrigatório, nesse caso tem que gerar um default pra ele
      exemplo3:  PropTypes.string,
      exemplo4:  PropTypes.number,
      exemplo5: PropTypes.func,

    }
    ```

# Instalando json-server
  - npm install json-server
  - depois de instalado criar um arquivo chamado db.json, vai ser nesse arquivo que será guardado os dados do "banco de dados"
  - No packager.json em scripts adicione o --->> "server": "json-server --watch db.json",
    Esse é o código para rodar
  - agora vc pode rodar com npm run server

# Instalando concurrently
  - npm install --save-dev concurrently
  Permite usar dois comandos que travam o terminal, assim vc pode rodar o server e o start
  - No package.json em scripts em dev 
    ----- "concurrently \"command1 arg\" \"comamand2 arg\"",
    -->>> "concurrently \"react-scripts start\" \"npm run server\"",
    - mudar o --> "server": "json-server --watch db.json",
      para -----> "server": "json-server --watch db.json--port 8080",
  - agora roda com --> npm run dev

# Hooks
  - https://pt-br.reactjs.org/docs/hooks-reference.html#defer-formatting-debug-values

  ## useEffect
    Agente chama ele quando quisermos que um efeito colateral aconteça. Serão dois parametros, o primeiro é o que vc quer que aconteça e o segundo é quando agente quer que aconteça.
    - import React, { useState, useEffect } from 'react'
    - Exemplo:
      useEffect (() => {
        console.log('testando');
      }, [
        value.nomes,
      ]);
      // nesse caso só vai ativar quando o value.nomes mudar.
      //se passar um array vazio no segundo parametro isso indica que agente só quer que aconteça uma vez
      //se não for passado nem um array ele vai executar em todas as atualizações que tiverem de componentes na tela, qualquer tecla ou coisa assim ativa ele.

  ## useState
  ## useHistory

# dataList

.find()

# Outras coisas
  ## Vercel
  ## Hiroku