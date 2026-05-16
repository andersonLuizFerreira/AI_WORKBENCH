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

## 5. Estrutura universal obrigatória

A IA deve validar e manter a estrutura universal mínima do projeto.

```text
REQUIRED_DIRECTORIES:
- .workbench/
- docs/
- dumps/
- tests/
```

REGRA:
Essas pastas devem existir em todo projeto governado pela AI_WORKBENCH.

VALIDAÇÃO:
Ao consumir este PROJECT_ENTRYPOINT.md, a IA deve verificar se todas as pastas em REQUIRED_DIRECTORIES existem no projeto local.

IF_MISSING:
Se qualquer pasta obrigatória estiver ausente, a IA deve criá-la automaticamente antes de continuar o fluxo.

BLOCKING_RULE:
A IA não deve iniciar engenharia, documentação, criação de skills, script de codação ou implementação enquanto a estrutura universal obrigatória estiver incompleta.

LIMITAÇÃO:
A estrutura universal não define ainda pastas específicas como src/, frontend/, backend/, firmware/, api/, database/ ou infra/. Essas pastas dependem da classificação e da engenharia do projeto.

## 6. Estrutura mínima obrigatória de docs

A pasta `docs/` é a fonte oficial de engenharia e arquitetura do produto.

A IA deve validar e manter a estrutura mínima de documentação.

```text
REQUIRED_DOCS_DIRECTORIES:
- docs/requirements/
- docs/architecture/
- docs/decisions/
- docs/validation/
```

REGRA:
A codação futura deve se basear na documentação e engenharia registradas em `docs/`.

VALIDAÇÃO:
Ao consumir este PROJECT_ENTRYPOINT.md, a IA deve verificar se todas as pastas em REQUIRED_DOCS_DIRECTORIES existem no projeto local.

IF_MISSING:
Se qualquer pasta obrigatória de docs estiver ausente, a IA deve criá-la automaticamente antes de continuar o fluxo.

RESPONSABILIDADES:

```text
docs/requirements/  -> requisitos, escopo e regras funcionais aprovadas
docs/architecture/  -> arquitetura, engenharia técnica, módulos, contratos e diagramas
docs/decisions/     -> decisões arquiteturais e registros ADR
docs/validation/    -> critérios de aceite, validação e evidências técnicas
```

BLOCKING_RULE:
A IA não deve criar script de codação nem implementar código de produto sem cobertura documental mínima em `docs/` para a etapa atual.

ESCALABILIDADE:
A estrutura de `docs/` nasce mínima. Novas subpastas especializadas só devem ser criadas após classificação e engenharia do projeto.

## 7. Workflow ativo

```text
ACTIVE_WORKFLOW: <workflow atual ou nao_definido>
NEXT_CONTEXT: .workbench/PROJECT_WORKFLOW.md
```

## 8. Regra de prioridade local/global

```text
LOCAL_RULE_PRIORITY:
As regras locais deste projeto sao verdadeiras enquanto sua cobertura existir.
Quando a cobertura acabar, consultar a WB antes de decidir.
```

## 9. Regras de bloqueio local

A IA deve parar se:

```text
- este arquivo possuir placeholders não preenchidos;
- PROJECT_WORKFLOW.md estiver ausente;
- CURRENT_STAGE.md estiver ausente;
- qualquer pasta em REQUIRED_DIRECTORIES estiver ausente e não puder ser criada;
- qualquer pasta em REQUIRED_DOCS_DIRECTORIES estiver ausente e não puder ser criada;
- o estágio atual estiver ambíguo;
- houver conflito entre regra local e regra global;
- a cobertura local acabar e não houver regra global aplicável.
```

## 10. Próximo passo obrigatório

Após ler este arquivo, a IA deve:

```text
1. validar REQUIRED_DIRECTORIES;
2. criar pastas obrigatórias ausentes, se necessário;
3. validar REQUIRED_DOCS_DIRECTORIES;
4. criar pastas obrigatórias de docs ausentes, se necessário;
5. ler .workbench/PROJECT_WORKFLOW.md;
6. ler .workbench/CURRENT_STAGE.md.
```

Depois deve seguir o workflow ativo registrado no projeto local.

## 11. Regra contra template cru

Este arquivo não deve ser consumido como contexto local válido se ainda contiver campos no formato:

```text
<campo pendente>
```

Se qualquer campo obrigatório estiver pendente, a IA deve retornar ao bootstrap e completar o preenchimento antes de continuar.
