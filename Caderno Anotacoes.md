




# Procurar informações sobre alguma propriedade css
    - Procurar no site da MDN. Ex.: mdn borda;
    - Ela tem a documentação oficial;


# CSS

`call to action (cta)`: é o botão que você quer que o usuário click (ex.: botão comprar)

- Criar um elemento HTML usando CSS: deve ser usado apenas para fins visuais sem conteúdo dentro.
    - `.header-store .action:after`: para criar um elemento depois.
    - `.header-store .action:befor`: para criar um elemento antes.
    - Dentro da chamada deve ter um `content: ""` (conteudo).
    ```
    .header-store .action:after {
        contet: "";
        ...
    }
    ```

- Nomenclatura de Classes:
    - Toda classe que começa com um `-` é uma variação (`.-second`). Já existe uma classe base e a variação apenas acrecenta e modifica o necessário para aquele elemento específico.
    - No css uma classe de variação deve ser chamada assim: `.button-store.-second`, dessa forma vc identifica que aquelas propriedades serão usadas apenas no elemento que tiver a classe principal junto da variação.
    - `.header-store .action` colocar a class do elemento pai dar um espaço e colocar a class que vc quer trabalhar é uma forma de garantir que só vai ser alterado o elemento q tiver essa classe dentro daquele pai especifico. Isso tambem ajuda ao navegador ir direto onde esta a classe se não ele vai verificar todos os elementos do html para ver se algum usa aquela classe tb.
    - `.header-store > .navigation` colocar o simbolo de maior (>) indica que vc quer o elemento que tenha esse pai e seja filho direto dele. Significa que esse elemento não vai estar dentro de um outro elemento filho. É uma forma mais direta ainda de mostrar onde ele está para o navegador.
    - `.item.-star + .item ` ira pegar o proximo `item` abaixo do `item.-star`, apenas ele. O sinal de mais (+) representa o abaixo. Dessa forma ele só vai selecionar o elemento com class `item` logo a baixo dele e não todos os class `item`.
    - `.header-store > input[type="search"]` ira selecionar o imput q seja filho do `.header-store` e que seja do tipo `search`.




# User Experience (UX)
- São técnicas para uma melhor experiencia para o usuário.

- affordance: é facil de usar se é intuitivo.

# Protocolo HTTP e HTTPS
- são protocolos (é a forma ou padrão defenidos para se comunicar no caso com o servidor)
- HTTP: agente entra com a url (http://facebook.com) o navegador faz uma requisição no servidor do endereço e o servidor retorna uma resposta.
    - http://facebook.com: http é o protocolo usado, o resto é o endereço (o dominio) do servidor.
    - No meio do caminho da requisição o navegador envia o dominio para um servidor DNS ele é responsavel por converter o nome do site para o numero de endereço fisico do servidor que esse site está. O DNS é quem sabe o caminho q vai ter q ser feito para chegar ao servidor do site.

- HTTPS: é o http seguro. Quando é feito uma requisição por https primeiro ele pede uma chave publica ( é uma chave q pode criptografar dados, porém ela não consegue descriptografar) para o servidor, dessa forma o navegador vai ter essa chave e o servidor vai ter outra chave q só serve para descriptografar.

# Protocolo SSH


# Valor de especificidade

- O css que está no topo tem menos prioriade do que os que vem abaixo dele. Isso quer dizer q ele da mais prioridade pela ordem de leitura.
- O de baixo vai sobreescrever o de cima.
- Cada seletor adicionado para chamar um elemento no css da mais prioridade para aquele codigo. 
```
.button-store. - second{
    color: blue;
}
.button-store {
    color: red;
}
```
No caso a cima o elemento vai continuar azul mesmo que você tenha sobreescrevido ele logo a baixo, pq o primeiro seletor é mais especifico é por isso tem um valor maior de especificidade, o q vai dar a ele a prioridade. (10 + 10 contra só 10 do outro)

- Valores dos seletores:
    - Selector id -> 100
    - Selector class/ pseudo seletores -> 10
    - Selector tag -> 1

# Pixel

- Pixel fisico: é o valor da resolução que tem nas especificações do aparelho quando vc compra.

- Pixel CSS: é um tamanho diferente do pixel, usado em telas pequenas ele emula um tamanho mais adequado para cada pixel para que fique mais confortavel de se ver.
<meta name="viewpor" content="width=device-width" /> esse código faz o navegador começar a considerar pelo pixel CSS.

# API do Browser
- No meio do codigo javaScript vão ter codigos expecificos do navegador, isso é a API do Browser. São codigos que não vão ter se vc usar o js pra backend por exemplo. Esses codigos tem haver para oq vc está usando, não são nativos da linguagem.