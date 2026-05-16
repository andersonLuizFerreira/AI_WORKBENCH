# ENTRYPOINT — Project Bootstrap Workflow

Este workflow define como a AI_WORKBENCH deve iniciar, validar ou preparar um projeto alvo antes de qualquer engenharia, arquitetura, documentação ou implementação.

## 1. Propósito

Conduzir a IA na identificação da situação inicial do projeto e na criação ou localização do contexto local `.workbench`.

Durante este workflow, a autonomia da IA é sempre baixa e supervisionada, conforme:

```text
AI_WORKBENCH/skills/governance-rules/SKILL.md
```

## 2. Arquivos obrigatórios antes deste workflow

A IA deve ler:

```text
1. AI_WORKBENCH/ENTRYPOINT.md
2. AI_WORKBENCH/skills/governance-rules/SKILL.md
3. AI_WORKBENCH/templates/project-entrypoint-template.md
4. AI_WORKBENCH/templates/project-workflow-template.md
5. AI_WORKBENCH/templates/current-stage-template.md
```

## 3. Regra de execução direta

REGRA:
Durante bootstrap e documentação inicial, se a IA possuir acesso de escrita ao repositório alvo, ela deve executar diretamente no GitHub/repositório.

A IA NÃO deve gerar prompt para Codex nessa fase quando ela própria puder criar os arquivos necessários.

Prompt para Codex só deve ser gerado quando:

```text
- a IA não possuir permissão de escrita;
- a operação depender de execução local indisponível para a IA;
- a etapa já estiver na fase de codação;
- o usuário pedir explicitamente um prompt para Codex.
```

## 4. Sequência fixa da ETAPA inicial

A IA NÃO deve perguntar "o que deseja construir primeiro" durante o bootstrap inicial.

A sequência inicial é fixa:

```text
1. criar/validar a estrutura e arquivos da `.workbench` local;
2. criar/validar as pastas globais obrigatórias;
3. criar/validar a estrutura mínima de `docs/`;
4. criar e popular a documentação mínima inicial;
5. transferir o fluxo para engenharia do projeto.
```

A IA pode perguntar apenas dados faltantes necessários para executar essa sequência.

## 5. Regra de fallback para contexto local ausente

A IA deve sempre procurar primeiro:

```text
ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md
```

Se o arquivo existir e estiver válido:

```text
Usar o contexto local do projeto.
```

Se o arquivo não existir:

```text
A IA deve obrigatoriamente retornar aos templates oficiais da WB.
```

Template obrigatório:

```text
AI_WORKBENCH/templates/project-entrypoint-template.md
```

A IA deve então:

```text
1. ler o template oficial;
2. criar o PROJECT_ENTRYPOINT.md local;
3. preencher os campos obrigatórios;
4. validar o preenchimento;
5. somente depois transferir o fluxo para o contexto local.
```

A IA não deve transferir o fluxo para um PROJECT_ENTRYPOINT.md vazio, incompleto ou contendo placeholders.

## 6. Primeira pergunta obrigatória

A IA deve perguntar ao usuário qual é a situação do projeto:

```text
1. Novo projeto sem repositório criado
2. Novo projeto com repositório já criado
3. Projeto existente
```

A IA não deve iniciar entrevista funcional antes de resolver essa classificação inicial.

## 7. Estrutura universal obrigatória

Durante o bootstrap, a IA deve criar e validar a estrutura universal mínima do projeto.

Pastas obrigatórias:

```text
.workbench/
docs/
dumps/
tests/
```

REGRA:
Essas pastas devem existir em todos os projetos governados pela AI_WORKBENCH.

VALIDAÇÃO:
Antes de concluir o bootstrap, a IA deve verificar se todas as pastas obrigatórias existem.

IF_MISSING:
Se alguma pasta obrigatória estiver ausente, a IA deve criá-la automaticamente antes de continuar.

LIMITAÇÃO:
A estrutura universal não define ainda pastas específicas como src/, frontend/, backend/, firmware/, api/, database/ ou infra/. Essas estruturas dependem da classificação e da engenharia do projeto.

## 8. Estrutura mínima obrigatória de docs

Durante o bootstrap, a IA deve criar e validar a estrutura mínima inicial de `docs/`.

Pastas obrigatórias:

```text
docs/requirements/
docs/architecture/
docs/decisions/
docs/validation/
```

REGRA:
Toda engenharia, arquitetura, documentação técnica e futura codação devem partir da pasta `docs/`.

VALIDAÇÃO:
Antes de concluir o bootstrap, a IA deve verificar se todas as pastas obrigatórias de docs existem.

IF_MISSING:
Se alguma pasta obrigatória de docs estiver ausente, a IA deve criá-la automaticamente antes de continuar.

LIMITAÇÃO:
A estrutura de `docs/` nasce mínima.

Subpastas especializadas adicionais só devem ser criadas após:

```text
- classificação do projeto;
- engenharia do projeto;
- necessidade real documentada.
```

## 9. Documentação mínima inicial

Durante a ETAPA inicial, a IA deve criar documentação mínima inicial dentro das subpastas corretas de `docs/`.

A IA NÃO deve criar arquivos soltos diretamente em `docs/` para substituir a estrutura mínima.

Sugestão de arquivos iniciais:

```text
docs/requirements/initial-requirements.md
docs/architecture/initial-architecture.md
docs/decisions/initial-decisions.md
docs/validation/initial-validation.md
```

A documentação inicial deve conter apenas o que já foi confirmado ou é estruturalmente necessário.

A IA não deve inventar requisito funcional nem decisão arquitetural não aprovada.

## 10. ROTA 1 — Novo projeto sem repositório criado

Quando o projeto ainda não possuir repositório remoto, a IA deve orientar o usuário a criar:

```text
- repositório Git remoto;
- pasta local do projeto;
- sincronização entre pasta local e repositório remoto;
- branch principal.
```

A IA deve orientar comandos ou passos equivalentes para:

```text
git clone
git status
git pull
git push
```

Se a IA/ferramenta não tiver acesso para criar o repositório remoto diretamente, deve orientar o usuário a criá-lo e solicitar a URL depois.

## 11. ROTA 2 — Novo projeto com repositório já criado

Quando o repositório remoto já existir, a IA deve solicitar:

```text
- nome do projeto;
- URL do repositório remoto;
- caminho local da pasta do projeto;
- branch principal, se conhecida.
```

Depois deve validar ou orientar validação de:

```text
- acesso de leitura ao repositório;
- acesso de escrita, quando necessário;
- pasta local existente ou clonável;
- sincronização Git;
- branch principal correta.
```

## 12. ROTA 3 — Projeto existente

Quando o projeto já existir, a IA deve solicitar o caminho local do repositório do projeto.

Depois deve procurar o contexto local da Workbench:

```text
ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md
ProjetoAlvo/.workbench/PROJECT_WORKFLOW.md
ProjetoAlvo/.workbench/CURRENT_STAGE.md
```

## 13. Projeto existente com `.workbench`

Se a pasta `.workbench` existir e os arquivos obrigatórios estiverem presentes, a IA deve:

```text
1. ler ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md;
2. ler ProjetoAlvo/.workbench/PROJECT_WORKFLOW.md;
3. ler ProjetoAlvo/.workbench/CURRENT_STAGE.md;
4. identificar a etapa atual;
5. continuar o projeto a partir do estado registrado.
```

O arquivo `CURRENT_STAGE.md` é obrigatório para continuidade.

Se `CURRENT_STAGE.md` estiver ausente ou ambíguo, a IA deve parar e tratar como falha de contexto local.

## 14. Projeto existente sem `.workbench`

Se o projeto existir, mas não possuir `.workbench`, a IA deve perguntar:

```text
Você deseja adequar este projeto às regras da AI_WORKBENCH?
```

Se a resposta for negativa:

```text
Encerrar o fluxo da Workbench para este projeto.
```

Se a resposta for positiva:

```text
Encaminhar para AI_WORKBENCH/workflows/project-adoption/ENTRYPOINT.md
```

A IA não deve criar engenharia, documentação ou código antes de seguir a política de adoção.

## 15. Criação da `.workbench` local

Quando a rota permitir criação inicial da `.workbench`, a IA deve criar no projeto alvo:

```text
.workbench/PROJECT_ENTRYPOINT.md
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

Esses arquivos devem ser preenchidos a partir dos templates oficiais da WB.

A IA deve:

```text
- usar os templates apenas como molde;
- substituir placeholders por dados reais;
- validar os campos obrigatórios;
- impedir transferência de fluxo com arquivos incompletos.
```

## 16. Conteúdo mínimo inicial

A `.workbench` inicial deve registrar apenas contexto mínimo:

```text
- nome do projeto;
- repositório remoto;
- caminho local;
- branch principal;
- repositório da WB de referência;
- status do bootstrap;
- próximo contexto local;
- etapa atual;
- próxima etapa.
```

A IA não deve inventar requisitos funcionais nessa etapa.

## 17. Saída obrigatória do bootstrap

Ao concluir o bootstrap, a IA deve apresentar:

```text
- rota identificada;
- repositório remoto validado ou pendente;
- pasta local validada ou pendente;
- branch principal;
- estrutura universal obrigatória criada e validada;
- estrutura mínima de docs criada e validada;
- documentação mínima inicial criada nas subpastas corretas;
- arquivos `.workbench` criados ou localizados;
- próximo arquivo a ser lido;
- bloqueios existentes, se houver.
```

## 18. Próximo contexto

Após bootstrap bem-sucedido, a IA deve transferir o fluxo para:

```text
ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md
```

A partir desse ponto, o projeto local passa a conduzir o fluxo, combinando:

```text
Regras globais da WB + contexto local do projeto alvo
```
