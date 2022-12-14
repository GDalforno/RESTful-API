
Este não é um projeto pessoal, serve para persistência do código do curso de Formação Node.js.

# API de Games

Esta API é utilizada para TAL e TAL...

## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK!  200
Caso essa resposta aconteça você vai receber a listagem de todos os games
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Call of duty MW",
        "year": 2019,
        "price": 60
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça. isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Toekn inválido, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token inválido"
}
```


### POST /auth
Esse endpoint é responsável por fazer o processo de login
#### Parametros
email: E-mail do usuário cadastrado no sistema.

passoword: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "email@email.com",
    "password": "1234"
}
```
#### Respostas
##### OK!  200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta:
```
{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJnYWJyaWVsQGRhbGZvcm5vLmNvbSIsImlhdCI6MTY3MDk2ODA5MiwiZXhwIjoxNjcxMTQwODkyfQ.7GUNQ0fSvUIKOK5OTrSgmS2NE3g5YKv54kQ1wvrngZg"}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça. isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: senha e/ou email errados

Exemplo de resposta:
```
{
    "err": "Credenciais inválidas"
}
```
