🏪 MVP2 – Sistema de Compras Online

Este projeto implementa um sistema de compras online baseado em componentização, utilizando duas APIs independentes que se comunicam entre si e com um serviço externo (FakeStore API).

O objetivo é demonstrar arquitetura de microsserviços simples, com persistência em banco de dados e consumo de API externa.

🔗 Arquitetura

API de Clientes → CRUD de clientes (localhost:5002)

API de Compras → CRUD de compras (localhost:5001), integrando com a FakeStore API

FakeStore API (externa) → fornece dados de produtos (https://fakestoreapi.com
)

📊 Fluxo de comunicação:

[ Postman / Front ]
        ↓
   [ API Compras ] ←→ [ FakeStore API ]
        ↓
   [ API Clientes ]


⚙️ Como rodar com Docker Compose

Certifique-se de ter o Docker instalado e rodando.

Clone este repositório e entre na pasta mvp2_compras/.

Rode:

docker compose up --build


Acesse os serviços:

API de Compras → http://localhost:5001/compras

API de Clientes → http://localhost:5002/clientes

📁 Estrutura do Projeto
mvp2_compras/
├── api_clientes/
│   ├── app.py
│   ├── requirements.txt
│   ├── Dockerfile
│   └── README.md
├── api_compras/
│   ├── app.py
│   ├── requirements.txt
│   ├── Dockerfile
│   └── README.md
├── docker-compose.yml
├── flowchart.png
└── postman_collection.json   # opcional (para facilitar testes no Postman)

🧪 Testes com Postman

Se quiser testar rapidamente:

Importe o arquivo postman_collection.json no Postman.

Ele já vem configurado com as rotas Clientes e Compras, prontos para uso.

🌍 API Externa Utilizada

FakeStore API → https://fakestoreapi.com

Serviço público e gratuito.

Rota usada: /products/{id} para buscar informações de produtos.