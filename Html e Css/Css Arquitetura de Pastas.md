
itcss willian justen
RSCSS willian justen

# ITCSS: 
Um padrão de arquitetura de pastas
É uma forma de organizar os arquivos css em pastas.
- Esse padrão é representado por uma piramide invertida, essa piramide é dividida em 7 partes cada uma representa uma pasta.
- A ideia é que a pasta da base pode consumir recursos da pasta acima dela, essa pasta acima consome conteúdo da proxima pasta e assim em diante. Uma pasta ainda pode consumir seu proprio conteúdo.
- O que se deve evitar é uma pasta consumir conteúdo de outra abaixo dela.

## OOCSS (Object Oriented CSS)
- CSS Orientado a Objeto, a ideia é organizar os componentes do css como se ele fosse orientado a objetos.

- Dois pontos principais:
    - estrutura e visual
    - independência do container em relação ao conteúdo.

## Pastas da parte mais alto para a mais baixa.
 
    - LEMBRAR QUE O CONTEUDO NÃO É IMPORTANTE NESSE MOMENTO SOMENTE O ESTILO, dessa forma fica mais facil de identificar.

    1. Settings (configurações): sua proposta é armazenar variáveis que serão usadas por todas as outras pastas. Ex.: um arquivo só de cores, vc guarda elas em variáveis e usá em qualquer parte do projeto.
    Arquivos comuns: 
        - colors.js - guarda as cores usadas no site; 
        - sizes.js - guarda o tamanho de fontes, tamanho de bordas;
        - spacing.js - espaçamentos entre um elemento e outro;

    2. Tools (ferramentas): aqui terá armazenado function, funções de comportamentos comuns. Ex.: um arquivo base.js que guarda uma function responsabel por centralizar objetos na tela.
    Arquivos comuns: 
        - functions.js - 

    3. Generic: É responsavel por definir os padrões do browser, aqui fica o reset. Nesse nível todos os seletores são tags (genericas), não se usa nome de class.
    Arquivos comuns:
        - reset.css

    4. Base/Elements: aqui também só se usa seletores de tags. Seu ogjetivo é definir os padrões do site.
    Arquivos comuns:
        - index.js  
        Ex.: h1 {font-size: var(--definido-em-settings)}; body{font-family: var(--definido-no-settings)};

    5. Objects: Aqui fica os componentes, aqui já se utiliza seletores de classe. São componentes bem genéricos, são flexiveis e podem ser usados em mais de um ponto do site. Ex.: a tag <title> ela pode ser o titulo de um texto e tb ser usada dentro de um outro item em outro contesto.
        - Caracteristicas:
            - Simples (não guarda stados(stateless - não guarda dados, só a estrutura do css, se vc quiser por um texto nele isso tera que ser passado pra ele no momento da criação));
            - Reaproveitavel em vários contestos;
        - O que Evitar:
            - margin / padding / display: flex / position / float / posicionamentos em geral

    6. Components: seria bem parecido com a pasta Objects porém bem mais específico. Seria um item do site que mesmo sendo usado em outros pontos ele continua sendo igual. Só usa seletores de classe.
        - Caracteristicas:
            - Ele é reutilizavel, mas ele é limitado ao que ele é, o component não vai mudar (se for um header vai ser sempre um header não tem como mudar)
            - Normalmente o componets vai ser um container que dentra vão ter alguns objets, como por exemplo o header.
            - Eles tendem a ser mais complexos. Eles guardam stado (statefull) 
            - display: flex é interessante já que mexe com os filhos.
        - O que Evitar quando for o component em si (não se aplica ao que tem dentro dele):
            - margin / padding / position / float / posicionamentos em geral




   ## React: styled-components



- RSCSS: é uma arquitetura de componentes, usada muito junto do ITCSS.
    - Componente: é um conjunto de itens. Deve ser o mais simples possível.
    - Objetcs: cuida da parte estrutural, um componente pouco visual que mexe com a estrutura.
    - O padrão para nomear um objetcs ou um components usando RSCSS é `palavra-segunda` (uma palavra - outra palavra).
        - Já um item é nomeado só com uma palavra.


- Regras para nomear component e object:
    - Será sempre usado duas palavras para nomeá-los, a pasta usa camel case (PalavraSegunda), a classe usa - (palavra-sgunda)
    - Para nomear os filhos usasse somente uma palavra, porem na hora de chamar esse elemento no css sempre deve ser usado o nome do pai jundo do filho (.container-pai > .filho).