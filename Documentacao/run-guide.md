# Guia de Execução

Este documento fornece as instruções passo a passo para configurar e executar o ambiente de desenvolvimento do projeto **Hub do Torcedor**.

## 1. Pré-requisitos

Antes de começar, garanta que você tenha os seguintes softwares instalados na sua máquina:

* **Docker**
* **Docker Compose**

## 2. Executando o Ambiente Completo

O projeto é totalmente containerizado, o que simplifica a execução. O comando a seguir irá construir as imagens necessárias, criar e iniciar os contêineres para o backend e o banco de dados.

1.  Navegue até a pasta raiz do repositório `backend`.
2.  Execute o seguinte comando no seu terminal:
    ```bash
    docker compose up --build
    ```
    * O argumento `--build` força a reconstrução da imagem da aplicação caso haja alguma alteração no código ou nas dependências.
    * Espere até que os logs se estabilizem e mostrem que o banco de dados está pronto para aceitar conexões e que o servidor Uvicorn (FastAPI) está rodando.

## 3. Acessando a API e a Documentação

Com os contêineres em execução, a API estará acessível no seu navegador:

* **Documentação Interativa (Swagger UI):** Para ver e testar todos os endpoints da API, acesse:
    * [http://localhost:8000/docs](http://localhost:8000/docs)

## 4. Rodando os Testes Automatizados

Os testes do backend devem ser executados dentro do contêiner da aplicação para garantir consistência no ambiente.

1.  Com os contêineres já em execução (após o `docker compose up`), abra um **novo terminal**.
2.  Entre no shell do contêiner do backend com o seguinte comando:
    ```bash
    docker exec -it hub_torcedor_backend bash
    ```
3.  Dentro do contêiner, instale as dependências de desenvolvimento:
    ```bash
    pip install -r requirements-dev.txt
    ```
4.  Execute o `pytest`:
    ```bash
    pytest
    ```
    A saída deve indicar o número de testes que passaram e foram pulados (`skipped`).

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 29/09/2025 | Criação do documento com as instruções para executar o projeto e os testes. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |