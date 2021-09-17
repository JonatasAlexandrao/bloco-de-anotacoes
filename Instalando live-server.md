
# Live-server como dependente
- Instalando dessa forma o live-server fica atrelado ao projeto, assim quando for baixado esse projeto em outra maquina suas dependências vão junto.

## Instalação terminal
- npn i live-server --save-dev
  - o `i` é de instal
  - o `--save-dev` indica q esse pacote é só pra ser usado no ambiente de desenvolvimento. Cria uma nova chave no JSON do node.

  - No JSON do note em "scripts" adicionar a linha: "dev": "live-server"

  - No terminal é só digitar : npm run dev
    - Esse comando abre o live-server

