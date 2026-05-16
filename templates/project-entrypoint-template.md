# PROJECT_ENTRYPOINT.md

Este arquivo é o ponto de entrada operacional local do projeto.

Ele deve ser criado pela IA durante o bootstrap usando este template como molde, mas nunca deve ser deixado com placeholders não preenchidos.

## 1. Identidade do projeto

```text
PROJECT_NAME: <nome real do projeto>
PROJECT_REMOTE_REPOSITORY: <url real do repositorio>
PROJECT_LOCAL_PATH: <caminho local real>
PROJECT_MAIN_BRANCH: <branch principal real>
```

## 2. Referência da Workbench

```text
WB_REPOSITORY: <repositorio da AI_WORKBENCH usado como referencia>
WB_GLOBAL_ENTRYPOINT: AI_WORKBENCH/ENTRYPOINT.md
WB_BOOTSTRAP_WORKFLOW: AI_WORKBENCH/workflows/project-bootstrap/ENTRYPOINT.md
WB_GOVERNANCE_SKILL: AI_WORKBENCH/skills/governance-rules/SKILL.md
```

## 3. Estado local do projeto

```text
PROJECT_STATUS: <status atual>
PROJECT_TYPE: <novo | existente | legado_em_adocao>
BOOTSTRAP_STATUS: <pendente | concluido | bloqueado>
```

## 4. Arquivos locais obrigatórios

```text
LOCAL_ENTRYPOINT: .workbench/PROJECT_ENTRYPOINT.md
LOCAL_WORKFLOW: .workbench/PROJECT_WORKFLOW.md
LOCAL_CURRENT_STAGE: .workbench/CURRENT_STAGE.md
```

## 5. Workflow ativo

```text
ACTIVE_WORKFLOW: <workflow atual ou nao_definido>
NEXT_CONTEXT: .workbench/PROJECT_WORKFLOW.md
```

## 6. Regra de prioridade local/global

```text
LOCAL_RULE_PRIORITY:
As regras locais deste projeto sao verdadeiras enquanto sua cobertura existir.
Quando a cobertura acabar, consultar a WB antes de decidir.
```

## 7. Regras de bloqueio local

A IA deve parar se:

```text
- este arquivo possuir placeholders não preenchidos;
- PROJECT_WORKFLOW.md estiver ausente;
- CURRENT_STAGE.md estiver ausente;
- o estágio atual estiver ambíguo;
- houver conflito entre regra local e regra global;
- a cobertura local acabar e não houver regra global aplicável.
```

## 8. Próximo passo obrigatório

Após ler este arquivo, a IA deve ler:

```text
1. .workbench/PROJECT_WORKFLOW.md
2. .workbench/CURRENT_STAGE.md
```

Depois deve seguir o workflow ativo registrado no projeto local.

## 9. Regra contra template cru

Este arquivo não deve ser consumido como contexto local válido se ainda contiver campos no formato:

```text
<campo pendente>
```

Se qualquer campo obrigatório estiver pendente, a IA deve retornar ao bootstrap e completar o preenchimento antes de continuar.
