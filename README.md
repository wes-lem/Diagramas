# Diagramas

```mermaid
graph TD
    subgraph "Sistema de Adoção e Apadrinhamento Animal"
        subgraph "Subsistema: Cadastro de Animais"
            UC1["UC1: Cadastrar Animal"] -- (inclui) --> UC1.1["UC1.1: Gerenciar Fotos do Animal"]
            UC1 -- (estende) --> UC1.2["UC1.2: Editar Dados do Animal"]
            UC1 -- (estende) --> UC1.3["UC1.3: Excluir Animal"]
            UC1.2 -- (inclui) --> UC1.1
            A[/"Abrigo/Protetor"/] --> UC1
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

    note for UC1
        **User Story:** US01
        **Tipo:** CRUD Simples
        **Fluxo Normal:** Abrigo/Protetor acessa "Cadastrar Animal", preenche formulário, anexa fotos, salva.
    end
    note for UC1.1
        **Tipo:** Consulta Simples/CRUD (fotos)
        **Fluxo Normal:** Abrigo/Protetor seleciona/upload fotos.
    end
    note for UC1.2
        **Tipo:** CRUD Simples
        **Fluxo Normal:** Abrigo/Protetor seleciona animal, edita campos, salva.
    end
    note for UC1.3
        **Tipo:** CRUD Simples
        **Fluxo Normal:** Abrigo/Protetor seleciona animal, confirma exclusão.
    end

```mermaid
  graph TD
    start((start)) --> CadastrarAluno[Estado Atividade: Cadastrar Aluno];

    subgraph Partição: Aluno
        CadastrarAluno --> PreencherDadosAluno[Preencher dados - Nome CPF RG Endereco Telefone Email];
        PreencherDadosAluno --> SistemaGeraMatricula[Sistema gera numero de matricula];
    end

    SistemaGeraMatricula --> RealizarMatricula[Estado Atividade: Realizar Matricula];

    subgraph Partição: Secretaria/Administração
        RealizarMatricula --> EscolherCursoESerie[Escolher curso e serie];
        EscolherCursoESerie --> ConsultarTurmasDisponiveis[Consultar turmas disponiveis - vagas limitadas];
        ConsultarTurmasDisponiveis -- Vagas Disponiveis --> SelecionarTurma[Selecionar turma];
        ConsultarTurmasDisponiveis -- Sem Vagas --> NotificarSemVagas[Notificar falta de vagas];
        NotificarSemVagas --> fimNotificacao((fim notificacao));
        SelecionarTurma --> RegistrarDataMatricula[Registrar data da matricula];
    end

    RegistrarDataMatricula --> fimMatricula((fim matricula));


```
