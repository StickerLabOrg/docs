# Requisitos Elicitados - Hub do Torcedor

## Introdução

O aplicativo **Hub do Torcedor** é um sistema que visa oferecer aos fãs de futebol uma plataforma de entretenimento completa, combinando um álbum de figurinhas digital com um sistema de palpites em jogos reais. Para garantir que a aplicação atenda às necessidades e expectativas dos usuários, foram definidos uma série de requisitos funcionais (RF) e requisitos não funcionais (RNF) durante o processo de ideação do projeto. Esses requisitos desempenham um papel fundamental na definição do escopo do MVP (Produto Mínimo Viável) e na orientação do desenvolvimento da aplicação. Os requisitos elicitados vieram principalmente das técnicas de [Introspecção](https://pt.wikipedia.org/wiki/Introspec%C3%A7%C3%A3o) e [Brainstorming](https://pt.wikipedia.org/wiki/Brainstorming).

## Metodologia

A metodologia adotada envolveu a consolidação de todos os requisitos funcionais (RF) e requisitos não funcionais (RNF) definidos para o escopo do MVP em uma tabela estruturada. Nesta tabela, cada requisito é identificado por um ID exclusivo, categorizado como RF ou RNF para indicar seu tipo e acompanhado de um status de implementação para o MVP. Além disso, a tabela também rastreia a origem de cada requisito, destacando se ele foi obtido por meio de técnicas como a Introspecção (a visão do que um usuário esperaria) ou Brainstorming (a construção de ideias para a funcionalidade).

Essa abordagem de registro em tabela oferece uma visão organizada e estruturada dos requisitos do projeto, permitindo uma fácil referência e acompanhamento ao longo do ciclo de desenvolvimento. Ela promove a rastreabilidade, garantindo que todas as necessidades do projeto sejam devidamente consideradas e atendidas.

A legenda para cada sigla é a seguinte:

<div align="center">
<font size="3"><p style="text-align: center"><b>Tabela 1:</b> Legenda para a tabela 2 de requisitos do Hub do Torcedor. </p></font>

<table>
  <thead>
    <tr>
      <th style="text-align:center;">Tipo</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center;">RF</td>
      <td>Requisito Funcional</td>
    </tr>
    <tr>
      <td style="text-align:center;">RNF</td>
      <td>Requisito Não-Funcional</td>
    </tr>
    <tr>
      <td style="text-align:center;">IS</td>
      <td>Requisito elicitado pela Introspecção</td>
    </tr>
    <tr>
      <td style="text-align:center;">BS</td>
      <td>Requisito elicitado pelo Brainstorming</td>
    </tr>
  </tbody>
</table>

<p style="text-align: center"><b>Fonte:</b> Lucas, 2025</p>
</div>

## Tabela de requisitos elicitados para o MVP

<div align="center">
<font size="3"><p style="text-align: center"><b>Tabela 2:</b> Requisitos elicitados do aplicativo Hub do Torcedor</p></font>
</div>

| ID | Código | Descrição | Status | Rastreabilidade |
| :---: | :----: | --------------------------------------------------------------------------------------------- | :---------: | :-------------: |
| HT01 | RF | O administrador deve poder **criar** uma nova coleção de álbum (ex: "Brasileirão 2025"). | A Fazer | BS |
| HT02 | RF | O administrador deve poder **visualizar** todas as coleções de álbuns cadastradas. | A Fazer | BS |
| HT03 | RF | O administrador deve poder **atualizar** os dados de uma coleção de álbum existente. | A Fazer | BS |
| HT04 | RF | O administrador deve poder **excluir** uma coleção de álbum. | A Fazer | BS |
| HT05 | RF | O sistema deve permitir que um novo usuário se **cadastre** usando e-mail e senha. | A Fazer | IS |
| HT06 | RF | O sistema deve permitir que um usuário existente faça **login**. | A Fazer | IS |
| HT07 | RNF | A autenticação do usuário deve ser realizada via tokens **JWT (JSON Web Token)**. | A Fazer | BS |
| HT08 | RNF | As senhas dos usuários devem ser **armazenadas de forma segura** (com hash). | A Fazer | BS |
| HT09 | RF | O sistema deve **exibir os jogos** da rodada atual para o usuário. | A Fazer | IS, BS |
| HT10 | RNF | Os dados das partidas devem ser obtidos de uma **API externa** confiável. | A Fazer | BS |
| HT11 | RF | O usuário deve poder **submeter um palpite** de placar para um jogo futuro. | A Fazer | IS, BS |
| HT12 | RF | O usuário deve receber um **pacote de figurinhas inicial** ao se cadastrar. | A Fazer | BS |
| HT13 | RF | O usuário deve poder **visualizar as figurinhas** que possui em seu álbum. | A Fazer | IS |
| HT14 | RF | O sistema deve **premiar com figurinhas** os usuários que acertarem seus palpites. | A Fazer | BS |
| HT15 | RNF | A aplicação (backend, frontend, BD) deve ser **containerizada usando Docker**. | A Fazer | BS |
| HT16 | RNF | A interface do usuário deve ser **responsiva**, adaptando-se a telas de desktop e mobile. | A Fazer | IS |

<div align="center">
<font size="3"><p style="text-align: center"><b>Fonte:</b> Lucas Víctor, 2025</p></font>
</div>

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 25/09/2025 | Criação do documento e definição dos requisitos elicitados para o MVP. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |