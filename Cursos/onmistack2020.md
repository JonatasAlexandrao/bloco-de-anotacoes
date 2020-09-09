# Olhar depois 
  - display grid (aula01 1:24:44)
  - :focus-within (aula01 2:05:17) verifica se o input que está dentro desse bloco está com focus.
  - API REST
  - no terminal: npm add typeScript -D
  - insominia (aula02 44:00:00)
  - biblioteca path --> ajuda a configurar caminhos dentro da aplicação



# Aula 01 - inicio

  Usando typeScript os arquivos que antes seriam .js ou .jsx agora são .tsx

  - para escrever com o auxilio do emiti:
  img.hero-image (enter)
  resultado: <img src="" alt="" classname="hero-image" />
  img#hero-image para id
  img#idHero.hero-image para id e class

  - sempre que eu for importar um arquivo para o projeto o seu caminho deve ser passado começando com ./ caso ele esteja na mesma pasta ou ../ para voltar uma pasta.

  ## Css: 
    - no arquivo global.css colocar um font-size: 60% 
    Usando um padrão generico para a fonte quando vc alterar o size em lugares expecificos usando rem ele vai levar em consideração o tamanho padrão da fonte.
    Assim caso vc precise diminuir todas as fontes em uma proporção por igual basta alterar somente o arquivo global reduzindo o 60%.

  - Para usar a sintaxe do jsx é preciso importar o react sempre.
  - Componentes sempre são criados com letras maiúsculas.
  - Toda imagem tem que ser importada para ser usada no arquivo.

  ## Usando o react-router-dom
    - depois de instalar quando for importar o react-router-dom para usar no seu arquivo ele pode aparecer sublinhado de vermelho dando um erro por causa do typeScript para resolver isso basta instalar o que ele pede
    - npm add @types/react-rounter-dom -D

  ## Components
    - são pedaços da pagina que podem ser reaproveitados em outras, reutilizaveis.

  ## tipos para as propriedades passadas
    - vc pode passar propriedades para um componente que vc criou (<Botao texto='adicionar' />), mas usando typeScript vc precisa declarar quais os tipos que essas propriedades vão ser e se serão obrigatórias.
    No seu componente vc deve usar arrow function. E usar um conseito chamado interface.
    ```
    interface PageAlgumaCoisa {
      texto: string; //setou essa propriedade como uma string e obrigatória.
      testeNaoObrigatorio?: number; // o "?" indica não obrigatório.
    }
    // Atribuir essa interface para seu componente
    const PageHeader: React.FC<PageAlgumaCoisa> = (props) => {
      return(<...>)
    }
    ```
  
  ## props.children
    - é uma propriedade que todo componente tem que ira retornar todo o conteudo colocado entre as tags do componente.
    ```
    // esse h1 e o bla bla bla são os children
    
    <Cabecalho title='Aperte aqui!'>
      <h1>titulo da pagina</h1> 
      bla bla bla ...
    </Cabecalho>
    ```

# Aula 02 - back end

  - criar uma pasta chamada server
  - no terminal: npm int -y
  - criar dentro da server a pasta src
  - dentro de src criar o server.ts
  - no terminal: npm add typeScript -D
  - npx tsc --init
  - npx add ts-node-dev -D

  - no package.json
    acrescentar: "scripts": {
      "start": "tsnd --transpile-only --ignore-watch node_modules --respawn src/server.ts"
    }
  - npm start

  ## Dependencias
  - npm add express

  ```
  import express from 'express';
  const app = express();

  app.use(express.json()); //para poder usar .json

  app.get('/users', (request, response) => {
    const users =[
      {name: 'Diego', age: 25}
    ];
    return response.json(users);
  });
  app.listem(3333) //porta que ira ser usada
  ```
  Metodos:
  - GET: Buscar ou Listar uma informação
  - POST: Criar alguma nova informação
  - PUT: Atualizar uma informação existente
  - DELETE: Deletar uma informação existente

  Parametros:
  - Corpo (Request Body): Dados para criação ou atualização de um registro.
  - Route Params: Identificar qual recurso eu quero atualizar ou deletar.
  - Query Params: Paginação, listagens, filtros, ordenação

- Baixar o insominia para usar todos esse metodos e testar seu backend 

## Listar Funcionalidades
  ### Conexões
    - Rota para listar o totla de conexões realizadas; (pag principal)
    - Rota para criar uma nova conexão

  ### Aulas
    - Rotas para criar uma aula;
    - Rotas para listar aulas;
      - Filtrar por matéria, dia da semana e horário;

## SQL Lite (1:01:00 +-)
  - npm add knex sqlite3
    - o knex é uma dependencia que permite escrever os códigos do sql em formato javaScript
  - Cria uma pasta em src chamada database
  - Cria um arquivo chamado connection.ts
    ```
    import knex from 'knex';
    import path from 'path';

    const db = knex({
      client: 'sqlite3',
      connection: {
        filename: path.resolve(__dirname, 'database.sqlite')
      },
      useNullAsDefault: true,
    });

    export default db;
    ```
    - O sqlite grava o banco em um arquivo na sua aplicação

  - Migrations - controlam a versão do banco de dados (tipo um git)
  - DOCUMENTAÇÃO: www.knexjs.org

  ### Criando tabela exemplo
    - criar um arquivo dentro de database > migrations > 00_create_users.ts 
    - dica, quando for salvar um campo de horas no mando, converte ela pra minutos e usa esse valor.

    ```
    import Knex from 'knex';

    export async function up(knex: Knex) {
      return knex.schema.createTable('users', (table) => {
        table.increments('id').primary();
        table.string('name').notNullable();
        table.string('avatar').notNullable();
        table.string('whatsapp').notNullable();
        table.string('bio').notNullable();
      })
    }

    export async function down(knex: Knex) {
      return knex.schema.dropTable('users');
    }
    ```

  - Executar as mudanção no BD
    - no arquivo package.json em "scripts"
    "knex:migrate": "knex --knexfile.ts migrate:latest"
    "knex:migrate:rollback": "knex --knexfile.ts migrate:rollback"

  ### Para ver o banco no VScode
    - instalar a extenção SQLite
    
  ### Criando as rotas
    - em um arquivo chamado routes.ts
    ```
    import express from 'express';
    import ClassesControlller from './controllers/ClassesController';
    import ConnectionsController from './controllers/ConnectionsController';

    const routes = express.Router();
    const classesControllers = new ClassesControlller();
    const connectionsController = new ConnectionsController();

    routes.get('/classes', classesControllers.index);
    routes.post('/classes', classesControllers.create);

    routes.get('/connections', connectionsController.index);
    routes.post('/connections', connectionsController.create);

    export default routes;
    ```