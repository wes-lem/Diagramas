# Diagramas

```mermaid
  graph TD
    start((start)) --> ManterDadosProfessor[Estado Atividade: Manter Dados do Professor];

    subgraph Partição: Secretaria/Administração
        ManterDadosProfessor --> RegistrarProfessor[Estado Ação: Registrar Professor (CPF, RG, Endereço, Telefone, E-mail, Data Admissão)];
        RegistrarProfessor --> AlocarProfessorEmTurma[Estado Atividade: Alocar Professor em Turma];
        AlocarProfessorEmTurma --> SelecionarTurma[Estado Ação: Selecionar Turma];
        SelecionarTurma --> AlocarProfessor[Estado Ação: Alocar Professor];
        AlocarProfessor --> MonitorarAlocacao[Estado Atividade: Monitorar Alocação];
        MonitorarAlocacao -- [Professor precisa ser substituído] --> RegistrarHistoricoSubstituicao[Estado Ação: Registrar histórico de substituição (data início/fim professor substituído)];
        MonitorarAlocacao -- [Professor permanece] --> endPermanencia((end));
        RegistrarHistoricoSubstituicao --> SubstituirProfessor[Estado Atividade: Substituir Professor];
        SubstituirProfessor --> end((end));
    end

    subgraph Partição: Recursos Humanos
        ManterDadosProfessor -- [Professor Demitido] --> RegistrarDataDemissao[Estado Ação: Registrar data de demissão];
        RegistrarDataDemissao --> endDemissao((end));
    end

    style ManterDadosProfessor fill:#ace,stroke:#333,stroke-width:2px;
    style RegistrarProfessor fill:#ace,stroke:#333,stroke-width:2px;
    style AlocarProfessorEmTurma fill:#ace,stroke:#333,stroke-width:2px;
    style SelecionarTurma fill:#ace,stroke:#333,stroke-width:2px;
    style AlocarProfessor fill:#ace,stroke:#333,stroke-width:2px;
    style MonitorarAlocacao fill:#ace,stroke:#333,stroke-width:2px;
    style RegistrarHistoricoSubstituicao fill:#ace,stroke:#333,stroke-width:2px;
    style SubstituirProfessor fill:#ace,stroke:#333,stroke-width:2px;
    style RegistrarDataDemissao fill:#ace,stroke:#333,stroke-width:2px;
```
