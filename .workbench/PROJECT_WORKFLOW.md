# PROJECT_WORKFLOW — AI_WORKBENCH

## Projeto

AI_WORKBENCH

## Tipo de projeto

Framework de governança e engenharia operacional para agentes de IA aplicados ao desenvolvimento de software.

## Objetivo atual

Construir incrementalmente uma estrutura reutilizável para:

- governança de agentes de IA;
- workflows de engenharia;
- classificação de projetos;
- levantamento de requisitos;
- arquitetura orientada por contexto;
- documentação padronizada;
- skills operacionais;
- validação;
- auditoria;
- implementação controlada.

## Estratégia de crescimento

A AI_WORKBENCH deve crescer de forma:

- incremental;
- modular;
- desacoplada;
- testável;
- escalável;
- orientada a valor.

Cada nova feature deve:

1. possuir propósito independente;
2. possuir início e fim claros;
3. resolver um problema específico;
4. funcionar sozinha;
5. não depender de features futuras para existir;
6. poder ser reutilizada em outros workflows.

## Regra arquitetural principal

A Workbench não deve conter dados específicos de projetos clientes.

Ela deve conter apenas:

- estruturas;
- workflows;
- skills;
- checklists;
- regras;
- templates;
- padrões;
- processos;
- governança.

Os dados específicos pertencem ao projeto destino.

## Arquivos locais obrigatórios

Todo projeto governado pela AI_WORKBENCH deve possuir:

```text
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

## Estado atual

Fase inicial de fundação da Workbench.

## Features iniciais planejadas

- ENTRYPOINT operacional;
- workflow base;
- classificação de projetos;
- entrevista inicial;
- ramificação de workflows;
- templates mínimos;
- estrutura local `.workbench`;
- skill base do agente entrevistador;
- skill base do agente arquiteto;
- skill base do agente codador.
