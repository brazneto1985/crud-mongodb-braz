# CRUD MongoDB – Cadastro de Itens

Aplicação Node.js/Express com MongoDB para CRUD de itens (ex.: cadastro de produtos) com campos: `name`, `category`, `price`, `description`.

## Tecnologias
- Node.js + Express 5
- MongoDB + Mongoose 8
- Dotenv (variáveis de ambiente)
- CORS
- Nodemon (desenvolvimento)

## Como rodar localmente
1) Clone o repositório
   - `git clone <link-do-repositorio>`
   - `cd crud-mongodb-braz`

2) Instale as dependências
   - `npm install`

3) Crie um arquivo `.env` na raiz com as variáveis abaixo:
   ```env
   MONGO_URI=mongodb://localhost:27017/seu-banco
   PORT=3000
   ```
   - Ajuste `MONGO_URI` para a sua instância do MongoDB.

4) Inicie em modo desenvolvimento
   - `npm run dev`
   - O servidor sobe em `http://localhost:3000` (ou na porta definida em `PORT`).

5) Produção (opcional)
   - `npm start`

## Endpoints (Postman)
Base URL: `http://localhost:3000/api/items`

- GET `/` – Lista todos os itens
  - Exemplo: `GET http://localhost:3000/api/items`

- GET `/:id` – Busca um item por ID
  - Exemplo: `GET http://localhost:3000/api/items/665f1b...`

- POST `/` – Cria um novo item
  - Body (JSON):
    ```json
    {
      "name": "Teclado Mecânico",
      "category": "Periféricos",
      "price": 299.9,
      "description": "Switch azul, ABNT2"
    }
    ```
  - Campos obrigatórios: `name`, `category`.

- PUT `/:id` – Atualiza um item existente
  - Body (JSON): enviar os campos que deseja atualizar
    ```json
    {
      "price": 279.9,
      "description": "Switch azul, ABNT2, RGB"
    }
    ```

- DELETE `/:id` – Remove um item

### Códigos de resposta comuns
- 200 OK – Sucesso em listagem/busca/atualização/remoção
- 201 Created – Sucesso ao criar
- 400 Bad Request – Campos inválidos
- 404 Not Found – Item não encontrado
- 500 Internal Server Error – Erro inesperado

## Estrutura principal do projeto
- `server.js` – Configuração do Express, CORS, conexão MongoDB e montagem das rotas
- `routes/items.js` – Rotas CRUD de itens
- `models/Item.js` – Schema Mongoose do Item
- `package.json` – Scripts e dependências

## Scripts úteis
- `npm run dev` – Inicia com `nodemon` (desenvolvimento)
- `npm start` – Inicia com `node` (produção)

## Link do Repositório
- Substitua aqui pelo link após publicar: `<link-do-repositorio>`

## Entregáveis
- `README.md` (este arquivo)
- `server.js`
- `routes/items.js`
- `models/Item.js`
- `package.json`, `package-lock.json`
- `postman_collection.json` (não incluído neste repositório)
- `.env` (não incluído por segurança)

## Observações
- A API usa `MONGO_URI` e `PORT` do `.env` (em `server.js`).
- CORS habilitado por padrão.
