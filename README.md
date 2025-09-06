# Estudo documentação de APIs
Estudo sobre documentação de APIs REST.

##Endpoints:

### GET /games
Esse endpoint retorna a listagem de jogos no banco de dados.
#### Paramentros:
Nenhum
#### Respostas:
##### OK! 200
Caso essa resposta aconteça você irá receber a listagem de todos os games.

Exemplo de resposta:

```
{
    "games": [
        {
            "id": 1,
            "title": "GTA V",
            "year": 2010,
            "price": 98,
            "createdAt": "2024-06-16T22:22:39.000Z",
            "updatedAt": "2024-06-16T22:22:39.000Z"
        },
        {
            "id": 2,
            "title": "Guitar Hero II",
            "year": 2008,
            "price": 45,
            "createdAt": "2024-06-16T22:23:15.000Z",
            "updatedAt": "2024-06-16T22:23:15.000Z"
        },
        {
            "id": 3,
            "title": "League of Legends",
            "year": 2012,
            "price": 60,
            "createdAt": "2024-06-16T22:23:47.000Z",
            "updatedAt": "2024-06-16T22:23:47.000Z"
        },
        {
            "id": 4,
            "title": "Super Mario World",
            "year": 1994,
            "price": 20,
            "createdAt": "2024-06-16T22:24:14.000Z",
            "updatedAt": "2024-06-16T22:24:14.000Z"
        }
    ]
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, significa que aconteceu algua falha durante o processo de autencação. Motivos: Token inválido, Token expirado 

Exemplo de resposta:

```
{
    "Erro": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por autenticar o usuario
#### Parametros
email: Email do usuário 

password: Senha do usuário

Exemplo de body request:

```
{
    "email": "exemplo@email.com",
    "password": "*****"
}
```

#### Respostas:

##### OK! 200
Caso essa resposta aconteça, o usuário recebe um token JWT para acessar endpoints protegidos.

Exemplo de resposta: 

```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJwZWRyb0BkZXYuY29tIiwiaWF0IjoxNzE4NTkzMzQ3LCJleHAiOjE3MTg2MDA1NDd9.nmU0aWmVzaUPVlxOgcWZphpaQHBBPHATibJwmIuLS3M"
}
```

##### Bad Request 400
Caso essa resposta aconteça, significa que foram informados valores vazios ou incorretos.

Exemplo de resposta:

```
{
    "Err": "Preenchimento inválido"
}
```

###### Falha na autenticação! 401
Caso essa resposta aconteça, significa que alguma falha aconteceu durante a autenticação da requisição. Motivos: Usuário inválido ou senha inválida para o usuário cadastrado.

Exemplo de resposta:

```
{
    "Err": "Falha na autenticação"
}
```

 


