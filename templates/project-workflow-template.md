# PROJECT_WORKFLOW.md

WORKFLOW_STATUS: aguardando_classificacao

WORKFLOW_COMPLEXITY:
WORKFLOW_SPECIALIZATION:
ACTIVE_WORKFLOW_PATH:

DEFAULT_ENGINEERING_WORKFLOW:
AI_WORKBENCH/workflows/project-engineering/ENTRYPOINT.md

LOCAL_ENGINEERING_WORKFLOW:
.workbench/workflows/project-engineering/ENTRYPOINT.md

ENGINEERING_WORKFLOW_TEMPLATE:
AI_WORKBENCH/templates/project-engineering-workflow-template.md

AI_AUTONOMY_LEVEL:
AI_AUTONOMY_REASON:
AI_AUTONOMY_SCOPE:
AI_AUTONOMY_LIMITS:
HUMAN_APPROVAL_REQUIRED_FOR:

CURRENT_ENGINEERING_STATUS:
CURRENT_DOCUMENTATION_STATUS:
CURRENT_IMPLEMENTATION_STATUS:

NEXT_EXPECTED_STEP:

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

4. gerar o workflow local de engenharia

5. transferir o fluxo para o workflow local criado
```

LAST_GOVERNANCE_UPDATE:
