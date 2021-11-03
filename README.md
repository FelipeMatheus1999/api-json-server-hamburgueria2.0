# Base URL

url(https://api-hamburgueria.herokuapp.com/)

## Endpoints

Nessa API existem 3 endpoints que podem ser utilizados para cadastro, 2 endpoints que podem ser usados para login 1 para ver o menu e 1 para favoritos.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

body {
email: "teste@gmail.com",
password: "123456Aa@",
age: 21,
}

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

body {
email: "teste@gmail.com",
password: "123456Aa@"
}

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### menu

GET /menu

Qualquer pessoa tem acesso ao menu, é preciso estar logado para ler.

body: null, Authorization: "Bearer + token"

### z

GET /favorites

Qualquer pessoa tem acesso aos favoritos, não é preciso estar logado para ler.
