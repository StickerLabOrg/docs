### **Plano do MVP - Hub do Torcedor (TPPE)**

**Versão:** 2.0
**Data:** 27 de Setembro de 2025

#### **1. Resumo do MVP**
O objetivo do MVP não é entregar o projeto completo, mas sim uma **fatia vertical funcional** que prove que a ideia principal e a arquitetura funcionam de ponta a ponta. O foco é máximo no ciclo de valor mais importante para o usuário final, que é: **Ver um jogo -> Fazer um palpite -> Ganhar moedas por isso, para então trocar por pacotes de figurinhas.**

#### **2. Objetivo do MVP**
Entregar uma versão funcional e enxuta da aplicação que permita a um usuário se cadastrar, visualizar os jogos da rodada, submeter um palpite de placar e ser recompensado com **moedas virtuais**. O MVP deve validar a arquitetura (React + FastAPI + Docker + PostgreSQL), a integração com a API externa, a implementação de um **CRUD completo** (Coleções) e o ciclo da **economia virtual** (ganhar moedas e comprar pacotes).

#### **3. Princípio Norteador**
**"Menos é mais"**. Foco absoluto no fluxo de engajamento principal e nos requisitos técnicos essenciais, cortando funcionalidades secundárias para focar nas que são "obrigatórias" para a avaliação.

---

### **4. Funcionalidades ESSENCIAIS (Escopo do MVP)**

#### **Backend (FastAPI)**

* **[✓] Módulo de Administração de Coleções (CRUD):**
    * Endpoints para um `admin` gerenciar as coleções de álbuns: `POST`, `GET`, `PUT`, `DELETE /admin/colecoes/`.

* **[✓] Módulo de Usuários (Mínimo):**
    * `POST /register`: Cria um novo usuário, inicializando seu saldo de **moedas**.
    * `POST /token`: Faz login e gera um token de autenticação (JWT).

* **[✓] Módulo de Partidas e Palpites:**
    * `GET /partidas/rodada-atual`: Busca e retorna os próximos jogos.
    * `POST /partidas/{id}/palpitar`: Permite que o usuário envie seu palpite.

* **[✓] Módulo de Loja e Pacotes:**
    * `POST /loja/comprar-pacote` (Protegido):
        1.  Verifica se o usuário tem moedas suficientes.
        2.  Subtrai o custo do pacote do saldo do usuário.
        3.  Sorteia N figurinhas aleatórias da coleção ativa.
        4.  Adiciona as figurinhas sorteadas à coleção do usuário.
    * `GET /me/album` (Protegido): Retorna a lista de figurinhas que o usuário possui.

* **[✓] Lógica de Recompensa:**
    * Um script `processar_resultados.py` executado **manualmente** que compara palpites com resultados reais e **adiciona moedas** ao saldo dos usuários vencedores.

#### **Frontend (React)**

* **[✓] Páginas de Autenticação:** Cadastro e Login.
* **[✓] Página de Administração (Simplificada):** Formulário e tabela para o CRUD de Coleções.
* **[✓] Página Principal / Dashboard (Protegida):**
    * Exibição clara do **saldo de moedas** do usuário.
    * `Componente ListaDePartidas` para exibir jogos e permitir palpites.
* **[✓] Página da Loja (Simplificada):**
    * Exibe o pacote de figurinhas disponível e seu custo em moedas.
    * Contém um botão "Comprar" que chama a API do backend.
* **[✓] Página "Meu Álbum":**
    * `Componente MeuAlbumSimples` para exibir as figurinhas que o usuário possui.

#### **Infraestrutura e Banco de Dados**

* **[✓] Docker & Docker Compose:** Arquivo `docker-compose.yml` funcional.
* **[✓] Modelo de Dados (Mínimo):**
    * `colecoes`: id, nome, ano, ativo.
    * `usuarios`: id, email, senha_hash, is_admin, **moedas (int)**.
    * `figurinhas`: id, nome_jogador, numero, id_colecao (FK).
    * `usuario_figurinhas`: id_usuario, id_figurinha.
    * `partidas`: id, time_casa, time_visitante, data_jogo.
    * `palpites`: id_usuario, id_partida, palpite_gols_casa.

---

### **5. O que Fica de FORA do MVP (Corte Radical)**

* NÃO FAZER: Sistema de trocas entre usuários.
* NÃO FAZER: Diferentes tipos de pacotes na loja ou missões complexas.
* NÃO FAZER: Perfis de usuário customizáveis ou placares de líderes detalhados.
* NÃO FAZER: Tabela de classificação do campeonato.
* NÃO FAZER: Design complexo ou animações de abertura de pacote. **A funcionalidade é a prioridade.**

---

### **6. Fluxo de Demonstração do MVP Atualizado**

1.  **CRUD (Admin):** "Primeiro, como administrador, eu crio, leio, atualizo e deleto uma coleção de álbum, como a 'Brasileirão 2025'."
2.  **Cadastro (Usuário):** "Agora, como um novo usuário, eu me cadastro na plataforma."
3.  **Login e Visualização:** "Ao fazer login, vejo a tela principal com os jogos da rodada e meu saldo inicial de moedas."
4.  **Ação (Palpite):** "Vou palpitar que no jogo entre Time A e Time B o placar será 2 a 1."
5.  **Processamento (Desenvolvedor):** "Simulando o fim da rodada, executo o script de processamento. Ele verifica os palpites e distribui as recompensas em moedas."
6.  **Recompensa (Usuário):** "Ao atualizar a página, vejo que meu saldo de moedas aumentou!"
7.  **Ciclo da Loja (Usuário):** "Com minhas moedas, vou até a Loja e clico em 'Comprar Pacote'. Meu saldo de moedas diminui."
8.  **Resultado Final (Usuário):** "Vou para a página 'Meu Álbum' e vejo as novas figurinhas aleatórias que ganhei no pacote. O ciclo de jogo foi concluído com sucesso."

---
### Histórico de Versões

| Versão | Data | Descrição | Autor | Revisor |
| :----: | :------------: | ----------------------------------------------------------------------- | :---------: | :---------: |
| `1.0` | 25/09/2025 | Criação do documento e definição do escopo inicial. | Lucas Víctor | Lucas Víctor |
| `2.0` | 27/09/2025 | Refatora o escopo para incluir a economia de moedas e pacotes. | Gemini | Lucas Víctor |