
# Diagramas UML

Esta seção apresenta os diagramas UML que modelam a estrutura e o comportamento do sistema "Hub do Torcedor", conforme exigido pelo Passo 6 do checklist do projeto.

## 1. Diagrama de Classes

O diagrama abaixo modela as entidades do MVP, seus atributos e relacionamentos.

**Diagrama gerado via Mermaid:**
```mermaid
classDiagram
    direction LR
    class Usuario {
        -id: int
        -nome: String
        -email: String
        -is_admin: boolean
        -moedas: int
        -time_do_coracao: String
        +cadastrar(): void
        +login(): boolean
        +fazer_palpite(palpite: Palpite): void
        +editar_palpite(palpite: Palpite): void
        +excluir_palpite(palpite: Palpite): void
        +comprarPacote(): ArrayList~Figurinha~
    }
    class Palpite {
        -id: int
        -palpite_gols_casa: int
        -palpite_gols_visitante: int
        +verificarAcerto(partida: Partida): boolean
    }
    class Partida {
        -id: int
        -time_casa: String
        -time_visitante: String
        -data_jogo: Datetime
        +get_status(): String
        +atualizar_resultado(gols_casa: int, gols_visitante: int): void
    }
    class Colecao {
        -id: int
        -nome: String
        -ano: int
        -ativo: boolean
        +criar(): void
        +listar(): ArrayList~Colecao~
        +atualizar(): void
        +excluir(): void
    }
    class Figurinha {
        -id: int
        -nome_jogador: String
        -numero: int
        -posicao: String
        -time: String
    }
    Usuario "1" -- "0..*" Palpite : gerencia
    Partida "1" -- "0..*" Palpite : refere-se a
    Colecao "1" *-- "1..*" Figurinha : é composta por
````



## 2\. Diagrama de Sequência

O diagrama a seguir ilustra o fluxo de interação entre os componentes do sistema durante o caso de uso **"Comprar Pacote de Figurinhas"**, um dos fluxos mais importantes da aplicação.



