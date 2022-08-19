```

const router = require('express').Router()

const OrdemDeServico = require('../models/OrdemDeServico')

router.get('/', async (req, res) => {

  try {
    //criando dados
    const ordemDeServico = await OrdemDeServico.find()

    res.status(200).json(ordemDeServico)
    
  } catch (error) {
    res.status(500).json({error: error})
  }


})

router.get('/:ID_pedido', async (req, res) => {

  try {
    //criando dados
    const id_pedido = req.params.ID_pedido
    const ordemDeServico = await OrdemDeServico.find({ID_pedido:id_pedido})

    res.status(200).json(ordemDeServico)
    
  } catch (error) {
    res.status(500).json({error: error})
  }


})

/*router.get('/:ID_pedido:nome', async (req, res) => {

  try {
    //criando dados
    const id_pedido = req.params.ID_pedido
    const nome = req.params.nome

    const ordemDeServico = await OrdemDeServico.find({nome:nome})

    res.status(200).json(ordemDeServico)
    
  } catch (error) {
    res.status(500).json({error: error})
  }


})*/

router.post('/', async (req, res) => {

const { ID_pedido, nome, celular, data_entrada, data_saida, valor_total, pago } = req.body

if(!ID_pedido) {
  res.status(422).json({ error: 'ID do serviço faltando'})
  return
}

const ordemDeServico = {
  ID_pedido,
  nome,
  celular,
  data_entrada,
  data_saida,
  valor_total,
  pago
}


try {
  await OrdemDeServico.create(ordemDeServico)

  res.status(201).json({message: 'Serviço criado com sucesso'})
  
} catch (error) {
  res.status(500).json({error: error})
  
}




})

router.patch('/:id', async (req, res) => {

  const id = req.params.id

  const { ID_pedido, nome, celular, data_entrada, data_saida, valor_total, pago } = req.body

  const ordemDeServico = {
    ID_pedido,
    nome,
    celular,
    data_entrada,
    data_saida,
    valor_total,
    pago
  }

  try {

    const updateOS = await OrdemDeServico.updateOne({_id:id}, ordemDeServico)

    if(updateOS.matchedCount === 0) {
      res.status(422).json({message: "Ordem de serviço não encontrada"})
      return
    }

    res.status(200).json({message: 'Ordem de serviço alterada com sucesso'})
    
  } catch (error) {
    res.status(500).json({error:error})
  }

})

router.delete('/:id', async (req, res) => {
  const id = req.params.id
  const ordemDeServico = await OrdemDeServico.findOne({ _id:id })

  if(!ordemDeServico) {
    res.status(422).json({ message: 'Ordem de serviço não encontrada.'})
  }

  try {

    await OrdemDeServico.deleteOne({_id:id})
    res.status(200).json({message: "Ordem de serviço removida com sucesso."})
    
  } catch (error) {
    res.status(500).json({error:error})
  }

})

module.exports = router

```