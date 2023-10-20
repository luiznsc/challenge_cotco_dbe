# SPRINT 1 | COT&CO | 2TDSPT
Entrega da sprint 1 | Digital Business Enablement

## LINK DO VÍDEO PITCH (CLIQUE NO ÍCONE ABAIXO):
[![YouTube Badge](https://img.shields.io/badge/YouTube-Watch-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/watch?v=f9yUR2hmyl0)

## DOCUMENTAÇÃO DA API

Documentação da API -
Essa API fornece funcionalidades básicas para gerenciar usários que usam o APP COT&CO.


*Usuário em nosso caso é o PROFISSIONAL DE COMPRAS que utilizará o app recorrentemente.*

### :heavy_plus_sign: CREATE USER

- **URL:** /cotco/users
- **Método:** POST
- **Descrição:** Cria um novo usuário.
- **Códigos de Status:**
  - :heavy_plus_sign: 201 (Created) - Usuário criado com sucesso.
  -  :warning: 400 (Bad Request) - Dados de entrada inválidos.
- **Corpo da Solicitação (JSON):**

  
  ```json
  {
    "nomeUsuario": "Nome do Usuário",
    "sobrenomeUsuario": "Sobrenome do Usuário",
    "emailUsuario": "email@cotco.com",
    "senhaUsuario": "senha123"
  }
 
---

### :repeat: UPDATE USER

- **URL:** /cotco/users/{id}
- **Método:** PUT
- **Descrição:** Atualiza os dados de um usuário existente.
- **Parâmetros da URL:**
  - {id} - ID do usuário a ser atualizado.
- **Códigos de Status:**
  - :white_check_mark: 200 (OK) - Usuário atualizado com sucesso.
  - :warning: 400 (Bad Request) - Dados de entrada inválidos.
  - :x: 404 (Not Found) - Usuário não encontrado.
- **Corpo da Solicitação (JSON):**

  
  ```json
  {
    "emailUser": "novo_email@cotco.com"
  }

---

### :page_with_curl: VIEW USER

- **URL:** /cotco/users/{id}
- **Método:** GET
- **Descrição:** Retorna os detalhes de um usuário específico.
- **Parâmetros da URL:**
  - {id} - ID do usuário a ser visualizado.
- **Códigos de Status:**
  - :white_check_mark: 200 (OK) - Detalhes do usuário retornados com sucesso.
  - :x: 404 (Not Found) - Usuário não encontrado.
- **Corpo da Resposta (JSON):**

  
  ```json
  {
    "idUsuario": 1,
    "nomeUsuario": "Nome do Usuário",
    "sobrenomeUsuario": "Sobrenome do usuario",
    "emailUsuario": "email@cotco.com"
  }
  
---

### :wastebasket: DELETE USER

- **URL:** /cotco/users/{id}
- **Method:** DELETE
- **Description:** Excluir um usuário existente
- **URL Parameters:**
  - {id} - ID do usuário a ser excluído.
- **Status Codes:**
  - :white_check_mark: 204 (No Content) - Usuário excluído com sucesso.
  - :x: 404 (Not Found) - Usuário não encontrado.
