# Diagramas

```mermaid
  graph TD
    start((start)) --> ManterDadosProfessor[Estado Atividade: Manter Dados do Professor];

    subgraph Partição: Secretaria/Administração
        ManterDadosProfessor --> RegistrarProfessor[Registrar Professor - CPF, RG, Endereco, Telefone, Email, Data Admissao];
        RegistrarProfessor --> AlocarProfessorEmTurma[Estado Atividade: Alocar Professor em Turma];
        AlocarProfessorEmTurma --> SelecionarTurma[Selecionar Turma];
        SelecionarTurma --> AlocarProfessor[Alocar Professor];
        AlocarProfessor --> MonitorarAlocacao[Estado Atividade: Monitorar Alocacao];
        MonitorarAlocacao -- Professor precisa ser substituido --> RegistrarHistoricoSubstituicao[Registrar historico de substituicao - datas];
        MonitorarAlocacao -- Professor permanece --> endPermanencia((end));
        RegistrarHistoricoSubstituicao --> SubstituirProfessor[Substituir Professor];
        SubstituirProfessor --> end((end));
    end

    subgraph Partição: Recursos Humanos
        ManterDadosProfessor -- Professor Demitido --> RegistrarDataDemissao[Registrar data de demissao];
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
