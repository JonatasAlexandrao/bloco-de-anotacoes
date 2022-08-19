
Link original: https://daveceddia.com/svelte-with-sass-in-vscode/

Use Svelte com SASS/SCSS no VSCode (exemplo + repositório clonável)
ATUALIZADA17 DE MARÇO DE 2020
Adicione suporte SASS para Svelte e vscode-svelte

Se você aprendeu a amar SASS/SCSS, você quer usá-lo em todos os lugares. O novo framework Svelte, embora empolgante, não tem suporte SCSS embutido. Mas é simples de adicionar!

Siga estas etapas para obter suporte SASS em seu aplicativo Svelte, além de obter destaque de sintaxe SASS no VSCode.

Adicionar suporte SASS ao projeto
A primeira peça desse quebra-cabeça é fazer com que seu projeto seja construído com o SASS ativado.

Começaremos com o modelo Svelte padrão, instalado com degit:

npx degit sveltejs/template svelte-with-sass
(a propósito, se você for executar este comando mais de uma ou duas vezes, recomendo instalar degitpermanentemente com npm i -g degitem vez de chamá-lo com npx. É muito mais rápido!)

Em seguida cd, no novo projeto, instale tudo e também instale o svelte-preprocesspacote, junto com o node-sass.

cd svelte-with-sass
npm install
npm install svelte-preprocess node-sass
Abra o rollup.config.jsarquivo que veio com o projeto. Há apenas algumas alterações a serem feitas:

// add this import at the top:
import preprocess from 'svelte-preprocess';


/* ... */


// and add preprocess as a plugin:
export default {
  /* ... */
  plugins: [
    svelte({
      /* ... */
      preprocess: preprocess()
    })
  }),
  /* ... */
}
Estamos importando o svelte-preprocesspré-processador automático e adicionando a preprocessetapa ao plugin svelte que já está lá. A ordem não importa aqui; Acabei de colocar a preprocesschave na parte inferior.

Salve esse arquivo e teste-o executando npm run dev. Tudo ainda deve funcionar.

Agora tente testá-lo com algum SCSS. Mudei App.sveltepara ficar assim:

<script>
  export let name;
</script>

<style lang="scss">
  $color: red;

  h1 {
    color: $color;
  }

  div {
    background: green;

    > p {
      color: #fff;
    }
  }
</style>

<h1>Hello {name}!</h1>

<div>
  <p>SASS is working!</p>
</div>
Depois disso, tente npm run devnovamente, abra a página e deve ficar algo (horrível) assim:

Uma página da web com Hello World vermelho e texto branco em um fundo verde mostrando que o SASS está ativado e funcionando

Aqui está um modelo inicial baseado no sveltejs/template, mas com as alterações aplicadas para que o SASS funcione: https://github.com/dceddia/svelte-sass-template . Você também pode usá-lo localmente com degit: degit dceddia/svelte-sass-template my-project.

Svelte com SASS no VSCode
Se você usa o VSCode, há algumas coisas a serem feitas para obter o realce da sintaxe SASS em seus arquivos Svelte.

Primeiro, certifique-se de ter a extensão Svelte for VSCode instalada.

Em seguida, abra as configurações do VSCode, digite “svelte” na caixa de pesquisa e procure esta opção chamada “Svelte > Language-server: Runtime”:

Encontrando a configuração do Svelte Language Server no VSCode

Na caixa, insira o local do seu binário Node.js.

Para descobrir onde fica:

Em um sistema Mac ou Linux, abra um terminal e executewhich node
No Windows, abra um terminal e digitewhere node
Pegue esse caminho e insira-o na caixa “Svelte > Language-server: Runtime”.

No meu Mac, é /usr/local/bin/node, mas o seu pode ser diferente, então não copie o meu cegamente ;)

Janelas…
Se você estiver no Windows, talvez seja necessário tomar medidas mais... drásticas.

Se o caminho do Node tiver um espaço (como C:\Program Files\nodejs\node.exe), você poderá ter mais sorte com o “caminho curto” como C:\Progra~1\nodejs\node.exe.

Além disso, tente escapar das barras com barras duplas, como C:\\Program Files\\nodejs\\node.exe.

Se isso ainda não funcionar, você pode ter alguma sorte em definir o caminho para algum rabisco que definitivamente falhará. Algo como C:/REMOVE_THIS_LATER. De acordo com @fvbixn no Twitter , isso fez com que o servidor falhasse inicialmente, mas depois ele tentou novamente e funcionou pela segunda vez. E também certifique-se de que comece com C:/ ou não funcionará. Muito estranho… mas ei, o que quer que funcione!

Crie o arquivo svelte.config.js
Verifique se você já instalou o módulo svelte-preprocess e o node-sass de antes e, em seguida, crie um arquivo na raiz do seu projeto chamadosvelte.config.js

// svelte.config.js
const preprocess = require('svelte-preprocess');

module.exports = {
    preprocess: preprocess(),
    // ...other svelte options could go here
};
(obrigado a Christan nos comentários por apontar isso e a Mark pelo pull request!)

Reinicie o VSCode
Depois disso, reinicie o VSCode. Você deve conseguir abrir o mesmo App.sveltearquivo de amostra que mostrei acima, com a sintaxe SASS, e não ver nenhum erro de sintaxe.

Defina o formato nas <style>tags
Certifique-se de adicionar lang="scss"a qualquer styletag onde você deseja usar o SCSS, como este:

<style lang="scss">
  /* ... */
</style>
(Ou para SASS, use lang="sass")

Sem isso, o Svelte não será compilado (o Rollup lançará erros em qualquer sintaxe SCSS) e o VSCode não destacará a sintaxe corretamente.

Divirta-se!

Se você quiser começar com o Svelte, confira meu tutorial de introdução ao Svelte . (O tutorial oficial também é excelente)


