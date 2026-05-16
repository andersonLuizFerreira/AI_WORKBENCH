# PROJECT_WORKFLOW.md

WORKFLOW_STATUS: aguardando_classificacao

WORKFLOW_COMPLEXITY:
WORKFLOW_SPECIALIZATION:
ACTIVE_WORKFLOW_PATH:

PROJECT_TECHNOLOGIES:
- <technology>

DEFAULT_ENGINEERING_WORKFLOW:
AI_WORKBENCH/workflows/project-engineering/ENTRYPOINT.md

LOCAL_ENGINEERING_WORKFLOW:
.workbench/workflows/project-engineering/ENTRYPOINT.md

ENGINEERING_WORKFLOW_TEMPLATE:
AI_WORKBENCH/templates/project-engineering-workflow-template.md

TECHNOLOGY_ENGINEERING_TEMPLATES:

```text
C#:
AI_WORKBENCH/templates/project-engineering/csharp-engineering-template.md

Angular:
AI_WORKBENCH/templates/project-engineering/angular-engineering-template.md

Arduino:
AI_WORKBENCH/templates/project-engineering/arduino-engineering-template.md
```

ENGINEERING_TEMPLATE_RULE:
Quando o projeto possuir tecnologias registradas em PROJECT_TECHNOLOGIES, a IA deve:

```text
1. identificar as tecnologias aplicáveis;
2. localizar os templates de engenharia correspondentes;
3. ler os templates tecnológicos;
4. compor o workflow local de engenharia;
5. adaptar a engenharia à stack tecnológica real do projeto.
```

AI_AUTONOMY_LEVEL:
AI_AUTONOMY_REASON:
AI_AUTONOMY_SCOPE:
AI_AUTONOMY_LIMITS:
HUMAN_APPROVAL_REQUIRED_FOR:

CURRENT_ENGINEERING_STATUS:
CURRENT_DOCUMENTATION_STATUS:
CURRENT_IMPLEMENTATION_STATUS:

NEXT_EXPECTED_STEP:

CONTINUITY_RULE:
A IA não deve encerrar o fluxo apenas recomendando a próxima etapa.

Quando não houver bloqueio, a IA deve:

```text
1. ler .workbench/PROJECT_ENTRYPOINT.md;
2. ler .workbench/PROJECT_WORKFLOW.md;
3. ler .workbench/CURRENT_STAGE.md;
4. identificar NEXT_EXPECTED_STEP;
5. executar ou encaminhar imediatamente para o workflow ativo aplicável;
6. atualizar CURRENT_STAGE.md ao final da ação executada.
```

A expressão "próxima etapa recomendada" só deve ser usada quando existir bloqueio, falta de permissão, necessidade de decisão humana ou pedido explícito do usuário para apenas planejar.

WORKFLOW_ROUTING_RULE:
Quando a etapa atual exigir engenharia e arquitetura, a IA deve:

```text
1. verificar se existe:
   .workbench/workflows/project-engineering/ENTRYPOINT.md

2. se existir:
   usar o workflow local do projeto

3. se não existir:
   usar:
   AI_WORKBENCH/templates/project-engineering-workflow-template.md

4. carregar templates tecnológicos aplicáveis

5. gerar o workflow local de engenharia

6. transferir o fluxo para o workflow local criado
```

LAST_GOVERNANCE_UPDATE:
