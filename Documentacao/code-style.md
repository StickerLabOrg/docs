# Guia de Estilo de Código

## Introdução

Este documento define as diretrizes e boas práticas de codificação para o backend do projeto **Hub do Torcedor**. O objetivo é manter um código limpo, legível, consistente e de fácil manutenção.

## 1. Ferramentas (Linting)

Para garantir a conformidade com as boas práticas, utilizaremos um linter. A ferramenta recomendada é o **Ruff** ou **Flake8**, que deve ser configurada para seguir o padrão de estilo **PEP 8**.

## 2. Princípios de Design (SOLID)
 O desenvolvimento do backend deve seguir, sempre que possível, os cinco princípios SOLID da Programação Orientada a Objetos.

* **S - Princípio da Responsabilidade Única (Single Responsibility):** Cada classe ou módulo deve ter uma, e somente uma, razão para mudar. Nossas classes `Controller`, `Model` e `View` seguem este princípio.
* **O - Princípio do Aberto/Fechado (Open/Closed):** As entidades de software (classes, módulos, funções) devem ser abertas para extensão, mas fechadas para modificação.
* **L - Princípio da Substituição de Liskov (Liskov Substitution):** Objetos de uma superclasse devem ser substituíveis por objetos de uma subclasse sem afetar a corretude do programa.
* **I - Princípio da Segregação de Interfaces (Interface Segregation):** Uma classe não deve ser forçada a implementar interfaces e métodos que não irá utilizar.
* **D - Princípio da Inversão de Dependência (Dependency Inversion):** Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações. O sistema de injeção de dependência do FastAPI (`Depends`) nos ajuda a aplicar este princípio.

## 3. Práticas de Orientação a Objetos

* **Responsabilidades Únicas:** Nossos controllers contêm a lógica de negócio, os models a persistência de dados e as views a camada de API.
* **Nomes Claros e Explícitos:** Variáveis, funções e classes devem ter nomes que descrevam claramente seu propósito (ex: `criar_nova_colecao` em vez de `cria_col`).

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 28/09/2025 | Criação do documento definindo as diretrizes de estilo de código e boas práticas. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |