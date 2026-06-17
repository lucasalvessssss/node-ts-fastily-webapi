<div align="center">

# 🏎️ F1 API - Fastify Edition

<p align="center">
Uma API REST simples desenvolvida com <b>Fastify</b> e <b>TypeScript</b> para fornecer informações sobre equipes e pilotos da Fórmula 1.
</p>

</div>

<br />

<div align="center">

![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)
![Fastify](https://img.shields.io/badge/Fastify-5.x-black.svg)
![Node.js](https://img.shields.io/badge/Node.js->=20-green.svg)

</div>

# 🚀 Technologies

Este projeto foi desenvolvido utilizando as seguintes tecnologias:

### 📦 Dependencies

* [TypeScript](https://www.typescriptlang.org/) - Superset JavaScript com tipagem estática.
* [Fastify](https://fastify.dev/) - Framework web rápido e eficiente para Node.js.
* [Node.js](https://nodejs.org/) - Ambiente de execução JavaScript.

### 📄 Estrutura de Dados

#### Teams

```json
{
  "id": 1,
  "name": "McLaren",
  "base": "Woking, United Kingdom"
}
```

#### Drivers

```json
{
  "id": 1,
  "name": "Lewis Hamilton",
  "team": "Mercedes"
}
```

### ⚡ Endpoints

#### 📋 Listar Equipes

```http
GET /teams
```

Resposta:

```json
{
  "teams": [
    {
      "id": 1,
      "name": "McLaren",
      "base": "Woking, United Kingdom"
    }
  ]
}
```

---

#### 👨‍✈️ Listar Pilotos

```http
GET /drivers
```

Resposta:

```json
[
  [
    {
      "id": 1,
      "name": "Lewis Hamilton",
      "team": "Mercedes"
    }
  ]
]
```

---

#### 🔎 Buscar Piloto por ID

```http
GET /teams/:id
```

Exemplo:

```http
GET /teams/1
```

Resposta de sucesso:

```json
{
  "driver": {
    "id": 1,
    "name": "Lewis Hamilton",
    "team": "Mercedes"
  }
}
```

Resposta de erro:

```json
{
  "message": "Driver not found"
}
```

# 👨‍💻 How To Use

Para executar o projeto localmente, você precisará ter o Node.js instalado.

```bash
# Clone este repositório
git clone <url-do-repositorio>

# Entre na pasta do projeto
cd nome-do-projeto

# Instale as dependências
npm install

# Execute o servidor
npm run dev
```

A aplicação será iniciada em:

```text
http://localhost:3333
```

# 📁 Estrutura do Projeto

```bash
src/
├── server.ts
├── routes/
├── controllers/
└── interfaces/
```

# ⚠️ Observações

Atualmente existe uma inconsistência na API:

```http
GET /teams/:id
```

Apesar do nome da rota indicar equipes (`teams`), ela retorna um piloto (`driver`).

O ideal seria alterar para:

```http
GET /drivers/:id
```

para manter a semântica REST mais consistente.

# 📌 Porta da Aplicação

```typescript
server.listen({ port: 3333 });
```

Servidor executando na porta:

```text
3333
```

# 👨‍💻 Autor

| Desenvolvedor |
| :-----------: |
|    Seu Nome   |

# 📄 Licença

Este projeto está disponível para estudos e aprendizado utilizando Node.js, TypeScript e Fastify.
