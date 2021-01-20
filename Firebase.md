Instalar no projeto o firebase
  `npm install firebase`

Criar uma pasta e um arquijo firebase.js
  - nele vc importa o firebase e add as configurações q vc pega do site do firebase.

```
import firebase from 'firebase/app'
import 'firebase/database'

const app = firebase.initializeApp({
  apiKey: "AIzaSyC_4H3TasdasdasdPGf_cw8CmyS-STSZSi8",
  authDomain: "pasdasda.firebaseapp.com",
  databaseURL: "https://asdasdpaesasdasdema",
  storageBucket: "aasdsdsd.appspot.com",
  messagingSenderId: "751270000514",
  appId: "1:75127:web:6b070cccf42dbcab37c19b"
})

export const db = app.database()
```

# Comandos para pesquisa no Banco

## set()
  `db.ref('nomeTabelaBD/').set({objComOsDados})`
  Salva dados em uma referência específica e substitue os dados existentes. (Tipo um push)

## push().set()
  `db.ref('nomeTabelaBD/').push().set({objComOsDados})`
  Salva uma nova entrada no banco, criando uma chave aleatória

## on()
  ```
  db.ref('clientes/').on('value', (snapshot) => {
    snapshot.forEach(item => {
      let chave = item.key
      let dado = item.val()
      console.log(chave, dado)
    }
  }
  ```
  Ele busca o conteudo da tabela, mas vc precisa fazer um forEach para acessar seus itens e filtrar se for o caso.

## update()

## remove()