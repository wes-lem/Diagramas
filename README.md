```mermaid
graph TD
    subgraph "Sistema de Adoção e Apadrinhamento Animal"
        subgraph "Subsistema: Cadastro de Animais"
            UC1["UC1: Cadastrar Animal"]
            note for UC1 "User Story: US01\nTipo: CRUD Simples\nFluxo Normal: Abrigo/Protetor acessa 'Cadastrar Animal', preenche formulário, anexa fotos, salva."
            
            UC1.1["UC1.1: Gerenciar Fotos do Animal"]
            note for UC1.1 "Tipo: Consulta Simples/CRUD (fotos)\nFluxo Normal: Abrigo/Protetor seleciona/upload fotos."
            
            UC1.2["UC1.2: Editar Dados do Animal"]
            note for UC1.2 "Tipo: CRUD Simples\nFluxo Normal: Abrigo/Protetor seleciona animal, edita campos, salva."
            
            UC1.3["UC1.3: Excluir Animal"]
            note for UC1.3 "Tipo: CRUD Simples\nFluxo Normal: Abrigo/Protetor seleciona animal, confirma exclusão."
            
            A[/"Abrigo/Protetor"/]

            A --> UC1
            UC1 -- (inclui) --> UC1.1
            UC1 -- (estende) --> UC1.2
            UC1 -- (estende) --> UC1.3
            UC1.2 -- (inclui) --> UC1.1
        end
    end

    style UC1 fill:#ACE1AF,stroke:#000,stroke-width:2px,rx:5px,ry:5px
    style UC1.1 fill:#D3F3EE,stroke:#000,stroke-width:1px,border-radius:5px
    style UC1.2 fill:#D3F3EE,stroke:#000,stroke-width:1px,border-radius:5px
    style UC1.3 fill:#D3F3EE,stroke:#000,stroke-width:1px,border-radius:5px
    style A fill:#ADD8E6,stroke:#000,stroke-width:2px
    linkStyle 0 stroke-width:2px,fill:none,stroke:black;
    linkStyle 1 stroke-width:2px,fill:none,stroke:black;
    linkStyle 2 stroke-width:2px,fill:none,stroke:black;
    linkStyle 3 stroke-width:2px,fill:none,stroke:black;
    linkStyle 4 stroke-width:2px,fill:none,stroke:black;
```
