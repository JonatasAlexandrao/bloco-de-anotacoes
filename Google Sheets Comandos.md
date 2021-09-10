
# Referencias:
  - https://jvvoliveira.medium.com/manipulando-google-sheets-com-node-js-4a551c68b270


  ## Base:
  ```
  const { GoogleSpreadsheet } = require('google-spreadsheet');
  const credenciais = require('./credenciais.json');
  const arquivo = require('./arquivo.json');

  const getDoc = async () => {
      const doc = new GoogleSpreadsheet(arquivo.id);
      
      await doc.useServiceAccountAuth({
          client_email: credenciais.client_email,
          private_key: credenciais.private_key.replace(/\\n/g, '\n')
      })
      await doc.loadInfo();
      return doc;
  }
  ```

  ## Funçoes:

  - `doc.title`: traz o titulo;

  ### Add
  - `const sheet = doc.sheetsByIndex[0]`: traz qual é a  primeira planilha do arquivo;
  - `sheet.addRow({ info para add em formato json }).then(()=> console.log('dado salvo')`;

  ### Listar

  ```
  let sheet; 
    getDoc().then(doc => {
        sheet = doc.sheetsByIndex[0];
        sheet.getRows().then(rows => {
            rows.map(row => {
                console.log(row.nome);
            })
        })
    })
  ```

  ## Atualizar
  ```
  let sheet;
    getDoc().then(doc => {
        sheet = doc.sheetsByIndex[0];
        sheet.getRows().then(rows => {
            rows.map(row => {
                if(row.nome === "João Victor"){
                    row.nome = "Victor";
                    row.idade = 31;
                    row.email = "medium@joao.com"
                    
                    row.save().then(() => {
                        console.log('Dado atualizado!');
                    });
                }
            });
        })
    })
  ```


  ### Deletar

  ```
  let sheet; 
  getDoc().then(doc => {
      sheet = doc.sheetsByIndex[0];
      sheet.getRows().then(rows => {
          rows.map(row => {
              if(row.nome === "Victor"){
                  row.delete().then(() => {
                      console.log('Dado deletado!');
                  });
              }
          });
      })
  })
  ```
