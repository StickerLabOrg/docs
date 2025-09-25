# Documento de Arquitetura

## Introdução

Este documento descreve a arquitetura de software da plataforma **Hub do Torcedor**. O objetivo é fornecer uma visão geral de alto nível dos componentes do sistema, suas responsabilidades, interações e os padrões de design que guiam a sua construção. A arquitetura foi projetada para ser modular, escalável e manutenível, utilizando uma abordagem moderna de desenvolvimento web com separação clara de responsabilidades entre o cliente (frontend) e o servidor (backend).

## Visão Geral da Arquitetura

A plataforma adota uma **arquitetura de microsserviços desacoplada**, baseada em uma comunicação via API RESTful. Os principais componentes são:

1. **Frontend (Single-Page Application):** Uma aplicação rica e interativa que roda no navegador do usuário, construída com React. É responsável por toda a interface e experiência do usuário.
2. **Backend (API RESTful):** Um serviço responsável por toda a lógica de negócio, gerenciamento de dados e comunicação com serviços externos. Construído com FastAPI.
3. **Banco de Dados:** Um banco de dados relacional PostgreSQL, responsável pela persistência de todos os dados da aplicação.
4. **API Externa:** Um serviço de terceiros (ex: API-Football) que fornece os dados em tempo real sobre partidas e estatísticas de futebol.

A comunicação principal ocorre quando o Frontend envia requisições HTTP (ex: GET, POST) para o Backend, que por sua vez processa a requisição, interage com o Banco de Dados e retorna os dados em formato JSON.

### Diagrama da Arquitetura

O diagrama abaixo ilustra a interação entre os principais componentes do sistema.

<div align="center">

```mermaid
graph TD
    A[Usuário] -->|Interage via Navegador| B(Frontend <br> React SPA);
    B -->|Requisições HTTP/JSON| C(Backend <br> API RESTful FastAPI);
    C -->|Consultas SQL| D(Banco de Dados <br> PostgreSQL);
    C -->|Busca Dados Esportivos| E(API Externa de Futebol);
 ```
 </div>

<div align="center">
<font size="3"><p><b>Figura 1:</b> Diagrama de Arquitetura de Alto Nível</p></font>  
<font size="3"><p><b>Fonte:</b> Lucas Víctor, 2025</p></font>
</div>

## Padrão de Design: Model-View-Controller (MVC)

O projeto aplica os princípios do padrão de design MVC de forma distribuída entre o backend e o frontend, aproveitando o melhor de cada tecnologia.

<div align="center">
<font size="3"><p><b>Tabela 1:</b> Aplicação do Padrão MVC no Projeto</p></font>
</div>

| Componente MVC               | Responsabilidade no Backend (FastAPI)                                                                                   | Responsabilidade no Frontend (React)                                                                                        |
| :--------------------------- | :---------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------- |
| **Model (Modelo)**           | Classes **SQLAlchemy** que mapeiam as tabelas do banco de dados e contêm a lógica de negócio.                           | O **estado dos componentes**, gerenciado por hooks como `useState` e `useEffect`, que armazena os dados vindos da API.      |
| **View (Visão)**             | Esquemas **Pydantic** que definem a estrutura e formato dos dados de resposta (JSON).                                   | Os **Componentes e seu JSX**, que renderizam o HTML e formam a interface com a qual o usuário interage.                     |
| **Controller (Controlador)** | Os **Endpoints/Rotas** (`@app.get`, `@app.post`) que recebem as requisições, orquestram as ações e retornam a resposta. | As **funções e manipuladores de eventos** (`onClick`, `onSubmit`) dentro dos componentes que respondem às ações do usuário. |

<div align="center">
<font size="3"><p><b>Fonte:</b> Lucas Víctor, 2025</p></font>
</div>

### Estrutura de Diretórios Proposta

A estrutura de pastas do projeto refletirá diretamente o padrão MVC para garantir a organização do código.

**Backend (FastAPI):**

```
backend/
└── app/
    ├── models/         # (M) Modelos SQLAlchemy
    ├── schemas/        # (V) Esquemas Pydantic
    ├── routers/        # (C) Controladores (Endpoints)
    ├── services/       # Lógica de negócio extra
    ├── database.py     # Configuração do BD
    └── main.py         # Ponto de entrada da aplicação
```

**Frontend (React):**

```
frontend/
└── src/
    ├── components/     # (V) Componentes reutilizáveis (Botões, Cards)
    ├── pages/          # (V) Páginas completas (Login, Dashboard)
    ├── services/       # (C) Lógica de chamada à API
    ├── contexts/       # (M) Gerenciamento de estado global
    └── App.js          # Ponto de entrada da aplicação
```

## Tecnologias Utilizadas

* **Backend:** Python 3.9+, FastAPI, SQLAlchemy, Pydantic, Uvicorn.
* **Frontend:** JavaScript, React 18+, Axios.
* **Banco de Dados:** PostgreSQL 13+.
* **Infraestrutura e Ambiente:** Docker, Docker Compose.

## Histórico de Versões



| Versão |    Data    | Descrição                                                                     | Autor | Revisor |
| :----: | :--------: | ----------------------------------------------------------------------------- | :---: | :-----: |
|  `1.0` | 25/09/2025 | Criação do documento, definindo a arquitetura, o padrão MVC e as tecnologias. | [Lucas Víctor](https://github.com/Lucas13032003)| [Lucas Víctor](https://github.com/Lucas13032003)

