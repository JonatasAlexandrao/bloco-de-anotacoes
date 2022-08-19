
DOCUMENTAÇÃO DO MONGODB
https://www.mongodb.com/docs/manual/introduction/

# Create
  ## Criar uma nova coleção(uma tabela) no banco
  db.createCollection("item")

  ## criar um novo item (linha)
  db.item.insert({
    "name": "Item 1",
    "price": 10.0
  })


  ## criar múltiplos itens (linhas)
  db.item.insertMany([
    {
    "name": "Item 2",
    "price": 30.0
    },
    {
      "name": "Item 3",
      "price": 20.0
    }
  ])


# Find
  Serve para buscar no banco

  ## Retorna todos os itens
  db.item.find()

  ## Limita o retorno na quantidade passada
  Quantos resultados vc quer na resposta
  db.item.find().limit(2)

  ## Buscar por palavras ou ids
  db.item.find({_id: ObjectId("5fga48df84d9f499df98df")})

  ## Escolher quais campos da resposta serão retornados
  O numero 1 indica true
  O numero 0 indica false
  O _id por padrão vai aparecer, para sumir com ele atribua 0
  db.item.find({_id: ObjectId("5fga48df84d9f499df98df"), {_id: 0, name: 1}})

  ## Retorna a quantidade de itens
  db.item.find().count()

  ## Retorna o item com o name e price passados (AND)
  db.item.find({$and: [{name: "Item 12"}, {price: 30.00}]})

  ## Retorna o item com o name ou price passados (OR)
  db.item.find({$or: [{name: "Item 12"}, {price: 30.00}]})


  ## Retornar apenas itens maiores que 25
  db.item.find({price: {$gt: 25}})
  ## Retornar apenas itens maiores ou iguais a 25
  db.item.find({price: {$gte: 25}})

  ## Retornar apenas itens menores que 25
  db.item.find({price: {$lt: 25}})
  ## Retornar apenas itens menores ou iguais a 25
  db.item.find({price: {$lte: 25}})

  ## Retornar apenas itens que não tenham 25
  db.item.find({price: {$ne: 25}})

  ## Retornar apenas itens com o valor 20 ou 30
  db.item.find({price: {$in: [20.0, 30.0]}})
  ## Retornar apenas itens que não tenham 25 ou 30
  db.item.find({price: {$nin: [20.0, 30.0]}})


# Remove
  Remover um item da tabela
  db.item.remove({_id: ObjectId("6s8df4gsfd486gdfg8df)})

# Update
  Atualizar as informações de um item
  db.item.update(
    {_id: ObjectId("6s8df4gsfd486gdfg8df)},
    {$set: {name: "teste", price: 50.00}}
  )