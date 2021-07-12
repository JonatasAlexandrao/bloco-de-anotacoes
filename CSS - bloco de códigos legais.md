# Variaveis de cores
  html {
    --color-background-page: rgb(190, 190, 190);
    --color-background: #fcf0e9 ;
    --color-black: rgb(17, 9, 9);
    --color-white: rgb(245, 245, 245) ;
    --color-font: rgb(60, 60, 60);
  }

# Reset
  html { box-sizing: border-box; }
  *, *::before, *::after { box-sizing: border-box; }
  h1, h2, h3, p { padding: 0; margin: 0; }
  li { list-style: none; padding: 0; display: inline;}
  ul { padding: 0; }

# Definir tamanho do font-size da pagina para 10px para ficar facil usar o tamanho rem
  :root { font-size: 10px; }

# Esconde textos e itens de uso semantico para leitores de tela
  .sr-only { 
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0,0,0,0);
    white-space: nowrap;
    border-width: 0;

  }