# HTML5

É uma linguagem de marcação que tem as seguintes responsabilidades:

- Conteúdo; 
- Semântico (tags de forma correta) - Demarca o que é cada conteudo;
- Estrutura


# Informações sobre HTML

<p>O conteúdo no html se orienta da esquerda para a direita e de cima para baixo. Isso pode ser meio contra intuitivo com o eixo y. 

# Tags HTML

- `<!DOCTYPE html>`:    diz para o navegador q deve ser usado o html mais recente.
- `<html>`:             engloba o site todo
- `<h1>`:               define um titulo
- `<a href="">`:        define um link e passa pra onde ele vai mandar
- `<head>`:             cabeça - configurações do site
- `<meta charset="">`:  define o alfabeto usado, usar o "utf-8"
- `<link rel="stylesheet" href="">`: linka o arquivo css oa seu html
- `<title>`:            é o titulo do site q aparece na aba do navegador


<b>TAGS DE ESTRUTURA:</b>
- `<nav>`:     navegação - menus
- `<header>`:  cabeçalho da pagina
- `<div>`:     é uma tag visual, deve se dar preferencia para coisas visuais, como uma divisão de página.
 - `<dl>`:      (description list) é usada para englobar uma descrição (de um produto por exemplo).
    - `<dt>`:   (description title) titulo, nome do produto.
    - `<dd>`:   (define description) é a descrição em si do produto, sua definição.

<b>TAGS SEMANTICAS</b>
- `<strong>`:   serve para marcar que o que tem dentro dela é muito importante, para o navegador dar mais importancia a ela.    

# CSS

O css é uma linguagem de estilos, isso quer dizer que ela tem as seguintes responsabilidades:

- Visual
- Posicionamento

# Reset CSS

Os navegadores tem padrões proprios de comportamento para as tags HTML por causa disso a página pode aparecer de forma diferente em cada navegador. Para resolver isso você cria um arquivo css com um padrão de reset que vai deixar as tags todas com um mesmo padrao, assim a página aparece igual em todos os navegadores. 
*** Lembrando que a chamada do reset sempre deve vir primeiro que os outros arquivos css, se não ele vai sobrescrever o código.

# Propriedades CSS

- `clear`: right        limpa a linha a direita, como uma quebra de linha.

<b>CORES:</b>
- `color`:              muda cor do texto;
- `background-color`:   muda cor do fundo;
- `background-color: transparent`:   Deixa o fundo transparente;

<b>TEXTO:</b>
- `font-size`:          tamanho da fonte;
- `font-family`:        escolhe qual fonte será usada;
- `text-decoration`:    remove ou coloca grifados e outras decorações de texto;
- `text-align`:         alinhamento do texto (right, center...);
- `line-height`:        para alinhar verticamente o texto dentro de uma caixa. Só funciona se for uma unica linha, se o texto não for maior que a largura da caixa. Deve se repetir o valor do height da caixa.

# POSICIONAMENTO com CSS

- `float`: (flutuador, flutuar) ela tem dois valores `left` e `right`. 
    - Ele cria um novo contexto (passa a ocupar um espaço a frente como uma camada). 
    - Ele nunca vai esconder um conteúdo (ele ira empurar o texto paro o lado). 
    - Ele passa a definir a largura e a altura pelo tamanho do conteudo.
    - O pai vai ignorar a tag com float, dessa forma o tamanho do pai não vai mais seguir o tamanho desse filho.

- `overflow`:  hidden  (recalcula o contexto - hidden é escondido) se você tiver uma largura e uma altura definida, os elementos filhos q forem maior ficaram escondidos, não sairão de dentro do elemento pai.
    -  se você usar essa propriedade com os elementos filhos usando float ele vai ver q não tem nem um elemento no contexto comum e vai usar o contexto do float para recalcular os tamanhos.

- `padding`:  "respiro interno", ele é responsavel por dar um espaço das bordas do elemento pai, para não ficar grudado com ele.
    - padding pod ser usado individualmente: 
    ```
    padding-top: 50px; 
    padding-right: 50px; 
    padding-botton: 50px; 
    padding-left: 50px;
    ```
    - formas resumidas:
    ```
    padding: 50px 60px 95px 60px;

    padding: top/bottom right/left;
    padding: 55px 60px;

    padding: top right/left bottom;
    padding: 55px 60px 95px;

    padding: top/bottom/right/left;
    padding: 55px; 
    ```

- `margin`:  "respiro externo", é responsavel pelo espaço entre um elemento e outro, a distancia q um elemento fica um do outro.
    - tem todas as caracteristicas do padding.

    - `top` e `bottom`: empurram o elemento para cima / baixo com relação a página. Mexem com o eixo X.

    - `left` e `right`: empurram o elemento para esquerda / direita com relação a página. Mexem com o eixo Y.

    - `transform: translate(-50%)`: ele move a posição do elemento, como se mudasse o eixo do elemento, normalmente com o -50%, para o centro dele.

    - `auto`: Se for usado o valor auto o próprio navegador passa a calcular a posição que o elemento vai ficar, dessa forma se o tamanho do elemento mudar a posição muda junto pq é o navegador que está calculando.
        - `margin-left: auto`: vai posicionar o elemento encostado a direita, se for right vai para a esquerda... 
        - Centralizar: usar auto no margin-left e no margin-right.

<b>POSITION:</b>

- `position: absolute`: Ele cria um novo contexto(como se fosse uma camada). O conteúdo passa a definir o tamanho da largura e altura. O `top bottom left right` movem em relação a página.

# Seletores de tag

- `id`: são unicos, não pode ter outro elemento com o mesmo id. Usar id somente se for mesmo necessario.

- `class`: pode ser usada varias vezes para replicar as propriedades do css para varias tags. Sempre usar class.
    - Pode se por mais de uma class por tag. Ex.: `class="classe1 classe2"`. No css você pode chamalas separadamente.


# Unidades de medida CSS

- `px`: pixel (unidade absoluta);
- `%`: porcentagem(unidade dinâmica);


# Design

- Respiro: é o espaço que se dá de um elemento ou outro, podendo ser externo ou interno.






