

### **Plano do MVP - Hub do Torcedor (TPPE)**

**Versão:** .0
**Data:** 25 de Setembro de 2025

#### **1. Resumo do MVP**
O objetivo do MVP não é entregar o projeto completo, mas sim uma **fatia vertical funcional** que prove que a ideia principal e a arquitetura funcionam de ponta a ponta. O foco é máximo no ciclo de valor mais importante para o usuário final, que é: **Ver um jogo -> Fazer um palpite -> Ganhar uma figurinha por isso.**

#### **2. Objetivo do MVP**
Entregar uma versão funcional e enxuta da aplicação que permita a um usuário se cadastrar, visualizar os jogos da rodada, submeter um palpite de placar e ser recompensado com figurinhas. O MVP deve validar a arquitetura (React + FastAPI + Docker + PostgreSQL), a integração com a API externa e **demonstrar a implementação de operações CRUD completas** em uma entidade administrativa principal.

#### **3. Princípio Norteador**
**"Menos é mais"**. Foco absoluto no fluxo de engajamento principal e nos requisitos técnicos essenciais, cortando todas as funcionalidades "legais de ter" (nice to have) para se concentrar nas que são "obrigatórias" (must have) para a avaliação.

---

### **4. Funcionalidades ESSENCIAIS (Escopo do MVP)**

#### **Backend (FastAPI)**

* **[✓] Módulo de Administração de Coleções (CRUD):**
    * Endpoints protegidos (acessíveis apenas por um usuário `admin`) para gerenciar as coleções de álbuns disponíveis.
    * `POST /admin/colecoes/` **(Create)**: Cria uma nova coleção (ex: "Brasileirão 2025").
    * `GET /admin/colecoes/` **(Read)**: Lista todas as coleções existentes.
    * `PUT /admin/colecoes/{id}` **(Update)**: Altera os dados de uma coleção.
    * `DELETE /admin/colecoes/{id}` **(Delete)**: Remove uma coleção.

* **[✓] Módulo de Usuários (Mínimo):**
    * `POST /register`: Cria um novo usuário. O sistema associa o novo usuário à coleção que está marcada como "ativa" no momento.
    * `POST /token`: Faz login e gera um token de autenticação (JWT).

* **[✓] Módulo de Partidas e Palpites:**
    * `GET /partidas/rodada-atual`: Busca na API externa os próximos jogos e os retorna para o frontend.
    * `POST /partidas/{id}/palpitar` (Protegido): Permite que o usuário logado envie seu palpite para um jogo.

* **[✓] Módulo de Figurinhas (Mínimo):**
    * `GET /me/album` (Protegido): Retorna uma lista simples das figurinhas que o usuário possui.
    * **Lógica de Recompensa (Coração do MVP):** Um script `processar_resultados.py` executado **manualmente** pelo desenvolvedor após os jogos para comparar palpites com resultados reais e distribuir as figurinhas-prêmio.

#### **Frontend (React)**

* **[✓] Páginas de Autenticação:** Cadastro e Login.
* **[✓] Página de Administração (Simplificada, rota `/admin`):**
    * Acessível apenas ao usuário admin.
    * Exibe uma tabela com as coleções e botões de Editar/Excluir.
    * Contém um formulário para criar/editar coleções.
* **[✓] Página Principal / Dashboard (Protegida):**
    * `Componente ListaDePartidas`: Exibe os jogos e permite o envio de palpites.
    * `Componente MeuAlbumSimples`: Exibe as figurinhas que o usuário possui. Uma simples lista de nomes (`"Neymar Jr. #10"`) é suficiente.
    * Um botão "Abrir Pacote Inicial" que dá ao usuário 5 figurinhas aleatórias.

#### **Infraestrutura e Banco de Dados**

* **[✓] Docker & Docker Compose:** Um arquivo `docker-compose.yml` funcional que sobe todo o ambiente.
* **[✓] Modelo de Dados (Mínimo):**
    * `colecoes`: id, nome, ano, ativo.
    * `usuarios`: id, email, senha_hash, is_admin (booleano).
    * `figurinhas`: id, nome_jogador, numero, id_colecao (FK).
    * `usuario_figurinhas`: id_usuario, id_figurinha (tabela de junção).
    * `partidas`: id, time_casa, time_visitante, data_jogo, gols_casa_real, etc.
    * `palpites`: id_usuario, id_partida, palpite_gols_casa, etc.

---

### **5. O que Fica de FORA do MVP (Corte Radical)**

* NÃO FAZER: Sistema de trocas, loja com moedas virtuais, missões complexas.
* NÃO FAZER: Perfis de usuário customizáveis ou placares de líderes.
* NÃO FAZER: Tabela de classificação do campeonato ou estatísticas detalhadas.
* NÃO FAZER: Atualização de placares em tempo real na tela.
* NÃO FAZER: Design complexo ou animações. **A funcionalidade é a prioridade.**

---

### **6. Fluxo de Demonstração do MVP Atualizado**

1.  **CRUD (Admin):** "Primeiro, vou me logar como administrador. Nesta área restrita, posso gerenciar as coleções. Vou **criar (CREATE)** a coleção 'Brasileirão 2025'."
2.  **CRUD (Admin):** "Como podemos ver, a coleção aparece na lista **(READ)**. Posso **alterar (UPDATE)** seu nome e, se necessário, **excluí-la (DELETE)**."
3.  **Cadastro (Usuário):** "Agora, como um novo usuário, vou me cadastrar na plataforma. O sistema automaticamente me atribui à coleção ativa que o administrador criou."
4.  **Login e Visualização (Usuário):** "Ao acessar, esta é a tela principal. Vemos os jogos da rodada e meu álbum, que pertence à coleção 'Brasileirão 2025' e tem apenas as figurinhas iniciais."
5.  **Ação (Palpite):** "Vou palpitar que no jogo entre Time A e Time B o placar será 2 a 1."
6.  **Processamento (Desenvolvedor):** "Simulando o fim da rodada, vou executar meu script de processamento no backend. Ele busca os resultados e distribui as recompensas."
7.  **Recompensa (Usuário):** "Ao atualizar a página do álbum, vemos que, como acertei o palpite, ganhei uma nova figurinha! O ciclo principal da aplicação foi concluído."


## Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 25/09/2025 | Criação do documento e definição do escopo | [Lucas Víctor](https://github.com/Lucas13032003) | [Lucas Víctor](https://github.com/Lucas13032003) |