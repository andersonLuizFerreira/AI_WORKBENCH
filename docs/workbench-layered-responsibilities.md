# Workbench Layered Responsibilities

## 1. Objetivo

A AI_WORKBENCH deve separar claramente:

- governança;
- engenharia;
- arquitetura;
- documentação;
- skills;
- execução de codação;
- validação;
- consolidação.

O objetivo dessa separação é impedir que:

```text
- regras arquiteturais se misturem com implementação;
- engenharia se misture com codação;
- IA implemente antes da definição estrutural;
- contexto operacional fique implícito;
- o projeto cresça sem rastreabilidade;
- agentes inventem continuidade fora da cobertura documental.
```

## 2. Conceito central

A Workbench não existe para gerar código.

Ela existe para:

```text
Transformar engenharia definida em implementação controlada.
```

A implementação deve ser consequência da engenharia.

Nunca o contrário.

## 3. Camadas da Workbench

A WB deve ser organizada em camadas independentes.

Cada camada possui responsabilidade própria.

## 4. Camada 01 — Governance

### Responsabilidade

Definir:

- regras globais;
- comportamento da IA;
- governança operacional;
- critérios de parada;
- autonomia;
- segurança contra alucinação operacional;
- fluxo universal da WB.

### Escopo

Essa camada NÃO conhece projetos específicos.

Ela define apenas:

```text
COMO agentes devem trabalhar.
```

### Exemplos

```text
skills/governance-rules/
ENTRYPOINT.md
workflows/project-classification/
```

## 5. Camada 02 — Project Bootstrap

### Responsabilidade

Criar o passivo inicial do projeto.

Inclui:

```text
- estrutura de pastas;
- arquivos iniciais;
- .workbench;
- entrypoints;
- templates mínimos;
- sincronização Git;
- contexto inicial.
```

### Objetivo

Garantir que o projeto possua uma fundação organizacional mínima antes da engenharia.

### Resultado esperado

```text
Projeto pronto para engenharia.
```

## 6. Camada 03 — Project Engineering

### Responsabilidade

Transformar ideia em engenharia estruturada.

Inclui:

```text
- entrevistas;
- levantamento de requisitos;
- análise técnica;
- análise de risco;
- definição de escopo;
- definição de fluxos;
- decisões arquiteturais;
- definição de módulos;
- contratos entre componentes;
- critérios de aceite.
```

### Regra central

A IA não deve implementar durante engenharia.

### Resultado esperado

```text
Engenharia suficientemente definida.
```

## 7. Camada 04 — Documentation

### Responsabilidade

Transformar engenharia em documentação rastreável.

### Fontes oficiais do projeto

A pasta `docs/` torna-se:

```text
Fonte oficial de arquitetura e engenharia do produto.
```

### Conteúdo esperado

```text
- requisitos;
- arquitetura;
- diagramas;
- ADRs;
- contratos;
- protocolos;
- modelos de dados;
- diagramas de classe;
- fluxos;
- critérios técnicos;
- padrões do projeto.
```

### Regra central

A IA não deve inventar comportamento fora da cobertura documental.

## 8. Camada 05 — Skills

### Responsabilidade

Transformar documentação e regras em comportamento operacional para agentes implementadores.

### Objetivo

Traduzir engenharia em regras executáveis por IA.

### Exemplos

```text
.codex/skills/
skills/
templates/
```

### As skills devem definir

```text
- o que pode fazer;
- o que não pode fazer;
- como validar;
- quais arquivos ler;
- quais padrões respeitar;
- quais bloqueios existem;
- quais regras são obrigatórias.
```

### Regra central

Skills não substituem documentação.

Skills operacionalizam documentação.

## 9. Camada 06 — Coding Scripts

### Responsabilidade

Transformar engenharia e documentação em sequência operacional de implementação.

### Conceito

A IA não deve “inventar o próximo passo”.

Ela deve seguir um roteiro explícito.

### O script de codação deve conter

```text
- etapa atual;
- objetivo;
- arquivos obrigatórios;
- skills obrigatórias;
- validações;
- limites da etapa;
- o que NÃO implementar;
- critérios de conclusão.
```

### Regra central

O script de codação é o contrato operacional da implementação.

## 10. Camada 07 — Validation

### Responsabilidade

Validar se a implementação respeitou:

```text
- documentação;
- arquitetura;
- skills;
- workflows;
- critérios de aceite;
- limites da etapa.
```

### A validação deve verificar

```text
- divergência arquitetural;
- acoplamento indevido;
- quebra de padrões;
- implementação fora do escopo;
- alucinação operacional;
- código não documentado;
- comportamento não previsto.
```

### Resultado esperado

```text
Implementação aprovada ou bloqueada.
```

## 11. Camada 08 — Consolidation

### Responsabilidade

Consolidar oficialmente a etapa concluída.

### Inclui

```text
- atualização da .workbench;
- atualização do CURRENT_STAGE;
- geração de relatórios;
- registro de decisões;
- atualização de workflows;
- fechamento de etapa;
- preparação da próxima etapa.
```

### Regra central

Nada deve virar “verdade oficial” sem consolidação supervisionada.

## 12. Estrutura conceitual completa

```text
AI_WORKBENCH
│
├── Governance
│
├── Bootstrap
│
├── Engineering
│
├── Documentation
│
├── Skills
│
├── Coding Scripts
│
├── Validation
│
└── Consolidation
```

## 13. Estrutura conceitual do projeto alvo

```text
Projeto/
│
├── .workbench/
│   Estado operacional do projeto
│
├── docs/
│   Fonte oficial de engenharia e arquitetura
│
├── .codex/
│   Skills e comportamento operacional do Codex
│
├── scripts/
│   Scripts operacionais de etapas
│
├── src/
│   Código-fonte
│
└── out/
    Relatórios e validações
```

## 14. Fluxo universal

```text
ENTRYPOINT
↓
Bootstrap
↓
Classificação
↓
Engenharia
↓
Arquitetura
↓
Documentação
↓
Skills
↓
Script de codação
↓
Implementação
↓
Validação
↓
Consolidação
↓
Próxima etapa
```

## 15. Regra mais importante da WB

```text
Código nunca deve ser a fonte de verdade.

A fonte de verdade deve ser:

engenharia
→ documentação
→ skills
→ script operacional
→ implementação
```

## 16. Regra de escalabilidade

A Workbench deve crescer:

```text
de forma incremental;
com baixa ambiguidade;
com responsabilidades separadas;
com rastreabilidade;
com mínima sobreposição entre camadas.
```

Novas regras não devem:

```text
- duplicar responsabilidades;
- misturar engenharia com implementação;
- misturar documentação com execução;
- misturar governança global com contexto local.
```
