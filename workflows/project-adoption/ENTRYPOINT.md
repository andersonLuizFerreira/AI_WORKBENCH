# ENTRYPOINT — Project Adoption Workflow

Este workflow define como a AI_WORKBENCH deve adequar projetos existentes que ainda não possuem `.workbench`.

## 1. Propósito

Permitir adoção gradual da AI_WORKBENCH sem destruir ou sobrescrever o contexto já existente do projeto.

## 2. Regra central

A IA não deve iniciar implementação ou reestruturação agressiva antes de compreender o estado real do projeto existente.

Projetos legados devem passar primeiro por:

```text
- inventário;
- leitura;
- análise;
- documentação;
- adequação gradual.
```

## 3. Arquivos obrigatórios antes deste workflow

A IA deve ler:

```text
1. AI_WORKBENCH/ENTRYPOINT.md
2. AI_WORKBENCH/skills/governance-rules/SKILL.md
3. AI_WORKBENCH/docs/workbench-layered-responsibilities.md
4. AI_WORKBENCH/workflows/project-bootstrap/ENTRYPOINT.md
```

## 4. Etapa 01 — Inventário inicial

A IA deve iniciar com inventário do projeto existente.

O inventário deve levantar:

```text
- estrutura de pastas;
- linguagens usadas;
- frameworks;
- existência de documentação;
- existência de diagramas;
- estrutura de módulos;
- estado do Git;
- tamanho aproximado do projeto;
- existência de testes;
- existência de CI/CD;
- dependências críticas;
- riscos aparentes.
```

## 5. Etapa 02 — Leitura da documentação existente

A IA deve localizar e ler:

```text
- README.md
- docs/
- ADRs
- diagramas
- comentários arquiteturais
- contratos
- protocolos
- documentação técnica existente.
```

A IA não deve assumir que ausência de documentação significa ausência de arquitetura.

## 6. Etapa 03 — Diagnóstico de adequação

A IA deve identificar:

```text
- lacunas de documentação;
- riscos arquiteturais;
- acoplamentos aparentes;
- padrões existentes;
- conflitos estruturais;
- ausência de rastreabilidade;
- necessidade de modularização;
- necessidade de governança local.
```

## 7. Etapa 04 — Proposta de adoção da WB

A IA deve apresentar proposta de adequação gradual.

A proposta deve incluir:

```text
- criação da `.workbench`;
- estratégia de documentação;
- estratégia de engenharia;
- estratégia de migração incremental;
- riscos da adequação;
- etapas futuras.
```

## 8. Etapa 05 — Criação da `.workbench`

Somente após aprovação humana, a IA deve criar:

```text
.workbench/PROJECT_ENTRYPOINT.md
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

A criação inicial deve registrar:

```text
status: projeto legado em adequação
```

## 9. Etapa 06 — Adequação documental

Antes de codificação, a IA deve:

```text
- adequar documentação mínima;
- organizar contexto arquitetural;
- registrar decisões;
- definir workflow inicial;
- definir autonomia local;
- registrar estágio atual.
```

## 10. Etapa 07 — Planejamento de implementação incremental

Somente após adequação mínima da documentação, a IA pode:

```text
- criar skills locais;
- criar scripts de codação;
- dividir etapas;
- planejar implementação incremental.
```

## 11. Regra central da adoção

A adoção da WB em projetos existentes deve ser:

```text
incremental;
rastreável;
supervisionada;
reversível;
com mínima destruição estrutural.
```

## 12. Próximo contexto

Após adequação mínima aprovada, a IA deve transferir o fluxo para:

```text
ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md
```
