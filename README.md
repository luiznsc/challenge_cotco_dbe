# SPRINT 3 | COT&CO | 2TDSPT
Entrega da sprint 3 | Digital Business Enablement
> [!NOTE]
> CRUD (Create, Read, Update e Delete) de uma empresa. A empresa é o nosso cliente direto, pois nossa solução é B2B.
> Análise de dados de um csv, responde ao método post trazendo o produto mais custo benefício considerando o nome inserido.


## DOCUMENTAÇÃO DA API

Documentação da API -
> Essa API fornece funcionalidades básicas para gerenciar empresas que utilizam o APP COT&CO. - Método Empresa Controller
> Análise de dados de um csv, responde ao método post trazendo o produto mais custo benefício considerando o nome inserido. - Método FileUploadController
---

### :heavy_plus_sign: CREATE COMPANY
>[!IMPORTANT]
> **Apenas os campos abaixo NÃO serão obrigatórios e podem estar vazios:** <BR/>
> 'complemento' (endereco) <BR/>

- **URL:** /cotco/empresas
- **Método:** POST
- **Descrição:** Cria uma nova empresa.
- **Códigos de Status:**
  - :heavy_plus_sign: 201 (Created) - Empresa criada com sucesso.
  -  :warning: 400 (Bad Request) - Dados de entrada inválidos.
- **Corpo da Solicitação (JSON):**

  
  ```json
    {
      "respEmpresa": "teste 2",
      "nmFantEmpresa": "Nome Fantasia da Empresa",
      "cnpjEmpresa": "22.111.1111/11",
      "telEmpresa": "(22)1111-1111",
      "emailEmpresa": "2teste2@gmail.com"
    }
 
---

### :repeat: UPDATE COMPANY
> [!IMPORTANT]
> **Poderão ser atualizados apenas os campos:** <BR/>
> NmFantEmpresa, <BR/>
> TelEmpresa,<BR/>
> EmailEmpresa, <BR/>
> Endereco

- **URL:** /cotco/empresas/{idEmpresa}
- **Método:** PUT
- **Descrição:** Atualiza os dados de uma empresa existente.
- **Parâmetros da URL:**
  - {idEmpresa} - ID da empresa a ter dados atualizados.
- **Códigos de Status:**
  - :white_check_mark: 200 (OK) - Empresa atualizada com sucesso.
  - :warning: 400 (Bad Request) - Dados de entrada inválidos.
  - :x: 404 (Not Found) - Empresa não encontrada.
- **Corpo da Solicitação (JSON):**

  
  ```json
    {
        "respEmpresa": "responsavel empresa",
        "nmFantEmpresa": "Nome Fantasia da Empresa",
        "emailEmpresa": "2teste2@gmail.com"
    }

---

### :page_with_curl: VIEW USER

- **URL:** /cotco/empresas
- **Método:** GET
- **Descrição:** Retorna os detalhes de todas empresas ativas no sistema
- **Parâmetros da URL:**
  - {idEmpresa} - ID da empresa ativa a ser visualizaoa, se desejar ver uma específica.
- **Códigos de Status:**
  - :white_check_mark: 200 (OK) - Detalhes das empresas retornados com sucesso.
  - :x: 404 (Not Found) - Empresa(as) não encontrada.
- **Corpo da Resposta (JSON):**

  
  ```json
    {
        "idEmpresa"
        "respEmpresa": "responsavel empresa",
        "nmFantEmpresa": "Nome Fantasia da Empresa",
        "cnpjEmpresa": "22.111.1111/11",
    }
  
---

### :wastebasket: DELETE COMPANY

> [!WARNING]
> **Ao chamar esse método a empresa NÃO DEVERÁ ser excluída, apenas ter o status alterado para INATIVA.** <BR/>
> **setando sua situacaoEmpresa para "inativa".**

- **URL:** /cotco/empresas/{idEmpresa}
- **Method:** DELETE
- **Description:** Tornar uma empresa existente como "INATIVA"
- **URL Parameters:**
  - {idEmpresa} - ID da empresa a tornar INATIVA.
- **Status Codes:**
  - :white_check_mark: 204 (No Content) - Empresa tornou-se INATIVA com sucesso.
  - :x: 404 (Not Found) - Empresa não encontrada.
