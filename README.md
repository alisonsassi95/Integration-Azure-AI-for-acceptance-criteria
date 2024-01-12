# **Projeto Hackathon-developer-2023**

O projeto Hackathon-developer-2023 visa abordar um desafio significativo enfrentado pelos Product Owners (P.O.s) das equipes, que frequentemente se deparam com a tarefa de redigir critérios de aceitação para as User Stories. Atualmente, essa é uma questão problemática na empresa, impactando a clareza para os desenvolvedores e dificultando o trabalho dos QA.

**Descrição do Sistema:**

O sistema foi desenvolvido em Python, utilizando o framework FAST API, com o objetivo de abordar um desafio específico no contexto do Azure DevOps. Ele automatiza o preenchimento dos critérios de aceitação para as User Stories que possuem o campo "Description" preenchido, mas o campo "Acceptance Criteria" vazio.

A integração ocorre através da página do FAST API, onde é possível inserir o ID da User Story desejada. Ao submeter o ID, o sistema utiliza a API da Open AI para treinar um modelo que gera automaticamente os critérios de aceitação mais adequados para a User Story em questão.

Essa abordagem visa facilitar o trabalho dos Product Owners (P.O.s) e equipes de desenvolvimento, proporcionando uma solução eficiente para a redação de critérios de aceitação, otimizando o processo e garantindo maior clareza nas tarefas a serem executadas.

Esta solução inovadora combina a praticidade do FAST API com a capacidade de treinamento de modelos da Open AI, proporcionando respostas assertivas e personalizadas para os requisitos de cada User Story no Azure DevOps.


**Demonstração em Vídeo:**

![GIF de Demonstração](Generate%20Cases.gif)

Acesse o arquivo [Generate Cases.gif](Generate%20Cases.gif) para visualizar a demonstração em vídeo do projeto.


## Configuração do Azure

Para utilizar este projeto, é necessário configurar as credenciais do Azure no arquivo `azure_config.py`. Substitua as variáveis pelos valores correspondentes:

```python
from azure.devops.connection import Connection
from msrest.authentication import BasicAuthentication

class AzureConfig:
    org_url = 'YOUR_URL_ORGANIZATION_OF_AZURE'  # Ex: 'https://dev.azure.com/YourOrganization'
    token = 'YOUR_TOKEN_OF_AZURE'
    project_id = 'PROJECT_OF_AZURE'  # Ex: 'YourProject'
Configuração da API OpenAI
```


Além disso, insira a chave de API da OpenAI no mesmo arquivo:

```python
class OpenIA:
    api_key = "YOUR_TOKEN_OF_OPENAI"
```

## Instalação

Siga os passos abaixo para configurar o ambiente e instalar as dependências:

Crie um ambiente virtual:

``` bash
python -m venv venv
```

* Ative o ambiente virtual:

No Windows:
```bash
source venv\Scripts\activate
```

No Linux/Mac:

```bash
source venv/bin/activate
```

* Instale as dependências:

```bash
pip install -r requirements.txt
```
* Execução

Para executar o projeto, utilize os seguintes comandos:

Ative o ambiente virtual:

No Windows:
``` bash
source venv\Scripts\activate
```

No Linux/Mac:

```bash
source venv/bin/activate
```

Inicie o servidor Uvicorn:

```bash

uvicorn main:app --reload
```

A aplicação estará disponível para uso após essas etapas. Certifique-se de substituir todas as variáveis pelos valores apropriados para garantir a correta integração com o Azure DevOps e a API OpenAI.
