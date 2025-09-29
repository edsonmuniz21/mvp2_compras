📄 README geral ( na raiz `mvp2_compras/README.md`)
# 🏪 MVP2 – Sistema de Compras Online

Este projeto implementa um sistema de compras online baseado em **componentização**, utilizando duas APIs independentes que se comunicam entre si e com um serviço externo (FakeStore API).

---

## 🔗 Arquitetura

- **API de Clientes** → CRUD de clientes (porta 5002)
- **API de Compras** → CRUD de compras (porta 5001), integrando com a FakeStore API
- **FakeStore API (externa)** → fornece dados de produtos

📊 Fluxo de comunicação:
[ Front/Postman ]
↓
[ API Compras ] ←→ [ FakeStore API ]
↓
[ API Clientes ]

yaml

---

## ⚙️ Como rodar com Docker Compose

```bash
docker compose up --build
API de Compras → http://localhost:5001/compras

API de Clientes → http://localhost:5002/clientes

📁 Estrutura
Copiar código
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
└── docker-compose.yml
yaml

---