# SPRINT 1 | COT&CO | 2TDSPT
Entrega da sprint 2 | Digital Business Enablement
> [!NOTE]
> Nessa entrega o sistema está preparado para fazer um CRUD (Create, Read, Update e Delete) de uma empresa. A empresa é o nosso cliente direto, pois nossa solução é B2B.


## DOCUMENTAÇÃO DA API

Documentação da API -
Essa API fornece funcionalidades básicas para gerenciar empresas que utilizam o APP COT&CO.

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
      "rzSocialEmpresa": "Company filial LTDA",
      "nmFantEmpresa": "Company Technologies",
      "cnpjEmpresa": "11.111.111.0001/01",
      "telEmpresa": "(11)91111-1111",
      "emailEmpresa": "comercial@companytech.com",
      "situacaoEmpresa": "true",
      "enderecoEmpresa" : {
          "logradouro": "Av Paulista",
          "bairro": "Bela Vista",
          "cep": "12345-123",
          "cidade": "São Paulo",
          "uf": "SP",
          "complemento":"",
          "numero": "1000"
      }
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
      "idEmpresa" : "1",
      "emailEmpresa": "comercialnovo@companytech.com"
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
    "idEmpresa": 1,
    "rzSocialEmpresa": "Company filial LTDA",
    "nmFantEmpresa": "Company Technologies",
    "cnpjEmpresa": "11.111.111.0001/01",
    "telEmpresa": "(11)91111-1111",
    "emailEmpresa": "comercial@companytech.com",
    "situacaoEmpresa": "true",
    "enderecoEmpresa" : {
        "logradouro": "Av Paulista",
        "bairro": "Bela Vista",
        "cep": "12345-123",
        "cidade": "São Paulo",
        "uf": "SP",
        "complemento":"",
        "numero": "1000"
    }
  }
  
---

### :wastebasket: DELETE COMPANY

> [!WARNING]
> **Ao chamar esse método a empresa NÃO DEVERÁ ser excluída, apenas ter o status alterado para INATIVA.** <BR/>
> **setando sua situacaoEmpresa para FALSE.**

> [!IMPORTANT]
> A coluna 'situacaoEmpresa' no banco aceitará 0 ou 1 <br/>
> **0 = ATIVA** <BR/>
> **1 = INATIVA**

- **URL:** /cotco/empresas/{idEmpresa}
- **Method:** DELETE
- **Description:** Tornar uma empresa existente como INATIVA
- **URL Parameters:**
  - {idEmpresa} - ID da empresa a tornar INATIVA.
- **Status Codes:**
  - :white_check_mark: 204 (No Content) - Empresa tornou-se INATIVA com sucesso.
  - :x: 404 (Not Found) - Empresa não encontrada.
