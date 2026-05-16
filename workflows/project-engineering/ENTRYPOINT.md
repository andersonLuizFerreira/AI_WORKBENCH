# ENTRYPOINT — Project Engineering Workflow

Este workflow governa a etapa de engenharia e arquitetura do projeto.

Ele deve ser executado após:

```text
- bootstrap concluído;
- PROJECT_ENTRYPOINT.md válido;
- PROJECT_WORKFLOW.md válido;
- CURRENT_STAGE.md válido;
- estrutura mínima de docs criada.
```

## 1. Propósito

Transformar uma ideia global em:

```text
- engenharia estruturada;
- arquitetura documentada;
- decomposição progressiva;
- documentação rastreável;
- unidades atômicas prontas para futura codação.
```

## 2. Regra central

A IA não deve implementar código de produto durante engenharia.

A função deste workflow é:

```text
entender
↓
quebrar
↓
documentar
↓
validar
↓
refinar
```

Somente depois:

```text
liberar futura codação.
```

## 3. Fonte oficial

A engenharia deve ser registrada em:

```text
docs/requirements/
docs/architecture/
docs/decisions/
docs/validation/
```

## 4. Ciclo progressivo

O fluxo deve ser iterativo:

```text
Ideia global
↓
Domínios
↓
Módulos
↓
Funcionalidades
↓
Casos de uso
↓
Tarefas técnicas
↓
Unidades atômicas
```

## 5. Regra de granularidade

A IA deve continuar quebrando o problema até remover ambiguidades técnicas críticas.

A IA deve parar a decomposição quando a unidade:

```text
- possuir objetivo claro;
- possuir escopo limitado;
- possuir documentação suficiente;
- possuir critérios de validação;
- possuir limites explícitos;
- estiver pronta para futura codação supervisionada.
```

## 6. Regra de bloqueio

A IA não deve gerar script de codação enquanto existir:

```text
- arquitetura indefinida;
- requisito ambíguo;
- regra técnica não aprovada;
- contrato indefinido;
- validação ausente;
- risco estrutural não tratado.
```

## 7. Workflow local

Projetos podem possuir um workflow local especializado em:

```text
.workbench/workflows/project-engineering/ENTRYPOINT.md
```

Quando existir, o workflow local possui prioridade operacional sobre este workflow global, desde que não conflite com as regras globais da WB.

## 8. Próximo contexto

Após engenharia suficiente, o próximo fluxo esperado será:

```text
AI_WORKBENCH/workflows/coding-script-generation/ENTRYPOINT.md
```

Se esse workflow ainda não existir, a IA deve parar e propor sua criação incremental.
