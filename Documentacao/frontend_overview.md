# Documentação do Frontend

## Introdução

Este documento descreve a arquitetura, as tecnologias e a estrutura do projeto frontend da plataforma **Hub do Torcedor**. A aplicação é uma **Single-Page Application (SPA)**, construída para oferecer uma experiência de usuário rica e interativa.

## Tecnologias Utilizadas

* **Framework Principal:** React 18+
* **Linguagem:** TypeScript
* **Build Tool:** Vite
* **Roteamento:** React Router DOM
* **Requisições HTTP:** Axios
* **Estilização:** CSS puro

## Estrutura de Pastas

[cite_start]O código-fonte da aplicação está organizado dentro da pasta `src/`, seguindo as melhores práticas para projetos React[cite: 262]:

* **`src/assets/`**: Para imagens, fontes e outros arquivos estáticos que são importados pelos componentes.
* **`src/components/`**: Contém componentes React reutilizáveis que formam os blocos de construção da UI (ex: `Button.tsx`, `Input.tsx`, `Header.tsx`).
* **`src/pages/`**: Contém os componentes que representam as páginas completas da aplicação (ex: `LoginPage.tsx`, `DashboardPage.tsx`).
* **`src/services/`**: Responsável por toda a comunicação com a API do backend. Centraliza as chamadas HTTP (ex: `api.ts`, `authService.ts`).
* **`src/styles/`**: Contém os arquivos de estilização CSS para os componentes e páginas.

## Fluxo de Autenticação

O fluxo de login, que conecta o frontend ao backend, funciona da seguinte forma:

1.  O usuário preenche o formulário na `LoginPage.tsx`.
2.  Ao submeter, a função `handleSubmit` formata os dados como `form-data`.
3.  O serviço `api` (configurado com Axios) envia uma requisição `POST` para o endpoint `/token` do backend.
4.  Se as credenciais estiverem corretas, o backend retorna um token de acesso (JWT).
5.  O frontend recebe o token, salva-o no `localStorage` do navegador e redireciona o usuário para a página principal (Dashboard) usando o React Router.

## Como Executar

Para executar o ambiente de desenvolvimento do frontend:

1.  Navegue até a pasta `frontend`.
2.  Instale as dependências: `npm install`
3.  Inicie o servidor: `npm run dev`

A aplicação estará disponível em `http://localhost:5173`.

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 28/09/2025 | Criação do documento de overview do frontend. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |