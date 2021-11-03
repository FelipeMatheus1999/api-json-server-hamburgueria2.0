# Base URL

url(https://api-hamburgueria.herokuapp.com/)

## Endpoints

Nessa API existem 3 endpoints que podem ser utilizados para cadastro, 2 endpoints que podem ser usados para login 1 para ver os favoritos e 1 para salvar o carrinho do usuário.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

body {
"name": "teste",
"email": "teste@gmail.com",
"password": "123456Aa@"
}

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

body {
"email": "teste@gmail.com",
"password": "123456Aa@"
}

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### favorites

GET /favorites

body: null
Authorization: false

Qualquer pessoa tem acesso aos favoritos, não é preciso estar logado para ler.

### cart

GET users/userId/cart

body: null
Authorization: true

POST users/userId/cart

body: {
"name": "Hamburguer",
"id": 1,
"price": 14,
"image": "../../assets/202109090436_skn5yx754p 1.png",
"category": "Sanduíches",
"number": 0
}
Authorization: true

PATCH /cart

body: {
"number": 1
}
Authorization: true

REMOVE /cart/itemId

body: null
Authorization: true

Somente o usuário poder ler os itens que tem no carrinho e ele precisa estar logado para escrever o item

Authorization: "Bearer + token"
