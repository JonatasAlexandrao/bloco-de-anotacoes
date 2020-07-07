# Abrir servidor no npm
- npm run dev

# Arquitetura de pastas
- components: são elementos reaproveitaveis usando as mesmas caracteristicas. Ele não é muito flexivel. 

# Procurar informações sobre alguma propriedade css
    - Procurar no site da MDN. Ex.: mdn borda;
    - Ela tem a documentação oficial;

# Criar uma nova ramificação no projeto
git checkout -b nomeDaRamificacao

# CSS

- variáveis no css são declaradas usando `--`. Ex.: `--color-first`.

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

# Funções Callback
- São funções que são passadas como parametros para outra função. São funcões chamadas como resposta de outro código.
- A função passada é uma callback:
    `teste(() => console.log('fn Callback'))`




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