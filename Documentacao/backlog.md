# Backlog

## Introdução

A metodologia ágil é uma abordagem flexível de gestão de projetos que se concentra na colaboração, adaptação e entrega contínua de valor. No contexto dessa metodologia, o Product Backlog desempenha um papel crucial. Ele é uma lista priorizada de requisitos, funcionalidades e tarefas que precisam ser executados em um projeto. O Product Backlog do nosso projeto está focado na divisão de grandes tarefas em Temas, Épicos e Histórias de Usuário, criando uma estrutura clara do trabalho a ser feito.

## Metodologia

A metodologia utilizada para a definição do Backlog do **Hub do Torcedor** parte inicialmente dos [requisitos elicitados](requisitos_elicitados.md). Através destes, identificamos grandes blocos de trabalho (Épicos) que se agrupam em objetivos estratégicos (Temas). Os Épicos são então detalhados em tarefas menores e focadas no valor para o usuário, as **Histórias de Usuário**.

## Backlog

### Temas

* **T01 - Gestão de Conta e Perfil:** Foco na experiência do usuário para acessar e gerenciar sua identidade na plataforma.
* **T02 - Jogo e Coleção:** Foco no ciclo principal de interação do usuário com o sistema de palpites, recompensas e o álbum de figurinhas.

### Épicos

* **EP01 - Gerenciamento de Conta:** Eu, como **usuário**, desejo gerenciar minha conta para acessar a plataforma de forma segura e personalizada.
* **EP02 - Interação com Partidas:** Eu, como **torcedor**, desejo interagir com as partidas reais para testar meu conhecimento.
* **EP03 - Coleção de Figurinhas:** Eu, como **colecionador**, desejo construir e gerenciar minha coleção de figurinhas digitais.

<div align="center">
<p><b>Tabela 1:</b> Tabela de backlog detalhada para a Entrega 1.</p>
</div>

<table>
  <thead>
    <tr>
      <th>ID</th>
      <th>História de Usuário</th>
      <th>Critérios de Aceitação (CA)</th>
      <th>Prioridade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>US01</b></td>
      <td>Eu, como visitante, quero poder me <b>cadastrar</b> na plataforma para ter um perfil.</td>
      <td>- Dado que preencho os campos (nome, email, etc.) corretamente, QUANDO clico em "Criar Conta", ENTÃO um novo usuário é criado no sistema.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US02</b></td>
      <td>Eu, como usuário, quero poder fazer <b>login</b> para acessar minha conta.</td>
      <td>- Dado que insiro um e-mail e senha válidos, QUANDO clico em "Entrar", ENTÃO sou autenticado e redirecionado para o Dashboard.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US03</b></td>
      <td>Eu, como usuário, quero ver meu <b>saldo de moedas</b> de forma visível na interface.</td>
      <td>- Dado que estou logado, QUANDO acesso o Dashboard, ENTÃO meu saldo atual de moedas deve ser exibido.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US04</b></td>
      <td>Eu, como torcedor, quero poder <b>visualizar os jogos</b> da próxima rodada.</td>
      <td>- Dado que estou no Dashboard, ENTÃO devo ver uma lista de partidas futuras.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US05</b></td>
      <td>Eu, como torcedor, quero poder <b>submeter um palpite</b> de placar para um jogo.</td>
      <td>- Dado que escolho uma partida, QUANDO insiro os placares e salvo, ENTÃO meu palpite deve ser registrado no sistema.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US06</b></td>
      <td>Eu, como torcedor, quero <b>ganhar moedas</b> como recompensa por meus acertos nos palpites.</td>
      <td>- Dado que fiz um palpite correto e a partida terminou, QUANDO acesso minha conta, ENTÃO meu saldo de moedas deve ter aumentado.</td>
      <td>Essencial</td>
    </tr>
     <tr>
      <td><b>US07</b></td>
      <td>Eu, como colecionador, quero poder <b>comprar pacotes</b> de figurinhas na loja usando minhas moedas.</td>
      <td>- Dado que tenho moedas suficientes, QUANDO clico em "Comprar Pacote", ENTÃO meu saldo é debitado e um pacote é adicionado à minha conta.</td>
      <td>Essencial</td>
    </tr>
     <tr>
      <td><b>US08</b></td>
      <td>Eu, como colecionador, quero poder <b>abrir um pacote</b> para descobrir minhas novas figurinhas.</td>
      <td>- Dado que possuo um pacote, QUANDO clico para abri-lo, ENTÃO uma interface revela as figurinhas aleatórias que ganhei.</td>
      <td>Essencial</td>
    </tr>
    <tr>
      <td><b>US09</b></td>
      <td>Eu, como colecionador, quero poder <b>visualizar meu álbum</b> e ver quais figurinhas eu tenho.</td>
      <td>- Dado que estou logado, QUANDO acesso a página "Meu Álbum", ENTÃO devo ver o progresso da minha coleção e a lista de figurinhas que possuo.</td>
      <td>Importante</td>
    </tr>
    <tr>
      <td><b>US10</b></td>
      <td>Eu, como usuário, quero poder fazer <b>logout</b> para encerrar minha sessão com segurança.</td>
      <td>- Dado que estou logado, QUANDO clico no botão "Sair", ENTÃO minha sessão é encerrada e sou redirecionado para a tela de login.</td>
      <td>Importante</td>
    </tr>
  </tbody>
</table>

<div align="center">
<p><b>Fonte:</b> Lucas Víctor, 2025</p>
</div>

## Bibliografia

> COHN, Mike. **User Stories Applied: For Agile Software Development.** Addison-Wesley Professional, 2004.
>
> SERRANO, Milene, SERRANO, Maurício. Requisitos (Aula 015): Elicitação, Modelagem e Análise. UnB Gama, Brasília, 2023.

## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 25/09/2025 | Criação do documento com 10 histórias de usuário iniciais. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |
| `2.0` | 28/09/2025 | Atualização das histórias para o sistema de moedas e adição de Critérios de Aceitação. | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |