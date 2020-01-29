




# Procurar informações sobre alguma propriedade css
    - Procurar no site da MDN. Ex.: mdn borda;
    - Ela tem a documentação oficial;


# CSS

`call to action (cta)`: é o botão que você quer que o usuário click (ex.: botão comprar)

- Nomenclatura de Classes:
    - Toda classe que começa com um `-` é uma variação (`.-second`). Já existe uma classe base e a variação apenas acrecenta e modifica o necessário para aquele elemento específico.
    - No css deve uma classe de variação deve ser chamada assim: `.button-store.-second`, dessa forma vc identifica que aquelas propriedades serão usadas apenas no elemento que tiver a classe principal junto da variação.
    - `.header-store .action` colocar a class do elemento pai dar um espaço e colocar a class que vc quer trabalhar é uma forma de garantir que só vai ser alterado o elemento q tiver essa classe dentro daquele pai especifico. Isso tambem ajuda ao navegador ir direto onde esta a classe se não ele vai verificar todos os elementos do html para ver se algum usa aquela classe tb.
    - `.header-store > .navigation` colocar o simbolo de maior (>) indica que vc quer o elemento que tenha esse pai e seja filho direto dele. Significa que esse elemento não vai estar dentro de um outro elemento filho. É uma forma mais direta ainda de mostrar onde ele está para o navegador.