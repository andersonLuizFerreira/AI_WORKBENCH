# SKILL — Governance Rules

Esta skill define regras operacionais transversais da AI_WORKBENCH.

Ela deve ser usada por agentes de IA sempre que houver classificação de projeto, definição de workflow, implementação controlada, auditoria, documentação ou atualização da `.workbench` local do projeto alvo.

## 1. Separação entre regra, heurística e exceção

### REGRA

Regra é obrigatória.

Use REGRA quando o agente deve obedecer sem reinterpretar.

Formato recomendado:

```text
REGRA:
<obrigação objetiva>

MOTIVO:
<por que existe>

APLICA-SE A:
<onde vale>

VALIDAÇÃO:
<como verificar>
```

### HEURÍSTICA

Heurística é recomendação orientadora.

Use HEURÍSTICA quando a decisão depende do contexto local do projeto.

Formato recomendado:

```text
HEURÍSTICA:
<recomendação>

USAR QUANDO:
<contexto esperado>

NÃO USAR QUANDO:
<contexto incompatível>
```

### EXCEÇÃO

Exceção é desvio permitido de uma regra, desde que justificado e registrado.

Formato recomendado:

```text
EXCEÇÃO:
<desvio permitido>

CONDIÇÃO:
<quando pode ocorrer>

REGISTRO OBRIGATÓRIO:
<onde registrar>
```

## 2. Critério de parada obrigatório

REGRA:
A IA deve parar sempre que houver decisão arquitetural, ambiguidade crítica ou risco de inventar regra.

A IA deve parar quando identificar qualquer uma das situações abaixo:

```text
- decisão arquitetural não registrada;
- ambiguidade crítica no objetivo, escopo, tecnologia ou fluxo;
- risco de criar regra sem fonte de verdade;
- conflito entre contexto local e regra global da WB;
- falta de arquivo obrigatório para a etapa;
- workflow recomendado inexistente;
- permissão insuficiente para validar ou alterar arquivos;
- implementação exigindo interpretação de negócio não confirmada;
- alteração estrutural não prevista na etapa atual.
```

Ao parar, a IA deve:

```text
1. declarar o bloqueio;
2. explicar a causa objetiva;
3. registrar a lacuna que impede avanço;
4. propor alternativas de decisão;
5. aguardar confirmação humana antes de continuar.
```

## 3. Nível de autonomia da IA

REGRA:
A WB não define um nível de autonomia global fixo para todos os projetos.

O nível de autonomia deve ser solicitado durante a classificação ou entrevista inicial e salvo no contexto local do projeto alvo.

Local recomendado:

```text
ProjetoAlvo/.workbench/PROJECT_WORKFLOW.md
```

Opcionalmente, projetos mais rigorosos podem registrar detalhes adicionais em:

```text
ProjetoAlvo/.workbench/AI_AUTONOMY.md
```

## 4. Níveis recomendados de autonomia

### AUTONOMIA BAIXA

A IA só pode executar ações após aprovação explícita da etapa.

Usar quando:

```text
- o projeto é crítico;
- há alto risco de retrabalho;
- existe arquitetura sensível;
- há hardware, firmware, protocolos, dados críticos ou legado importante;
- o operador humano quer controle fino.
```

### AUTONOMIA MÉDIA

A IA pode executar ajustes locais e tarefas pequenas dentro de uma etapa já aprovada.

Usar quando:

```text
- a arquitetura base já está definida;
- a etapa possui escopo claro;
- alterações pequenas não afetam decisões estruturais;
- há validação objetiva após execução.
```

### AUTONOMIA ALTA

A IA pode implementar com maior liberdade dentro de um escopo aprovado, desde que respeite regras, bloqueios e validações.

Usar quando:

```text
- o projeto é pequeno ou experimental;
- o risco estrutural é baixo;
- a perda por retrabalho é aceitável;
- há critérios claros de validação;
- o operador humano deseja velocidade.
```

## 5. Registro mínimo da autonomia no projeto alvo

O registro local deve conter no mínimo:

```text
AI_AUTONOMY_LEVEL: baixa | media | alta
AI_AUTONOMY_REASON: <justificativa curta>
AI_AUTONOMY_SCOPE: <onde vale>
AI_AUTONOMY_LIMITS: <limites explícitos>
HUMAN_APPROVAL_REQUIRED_FOR: <decisões que exigem aprovação>
```

## 6. Contrato executável de workflow

Todo workflow operacional da WB deve evoluir para o seguinte contrato mínimo:

```text
INPUTS
PRECONDIÇÕES
PROCESSO
OUTPUTS
PÓS-CONDIÇÕES
VALIDAÇÕES
BLOQUEIOS
CONFIRMAÇÃO HUMANA
PRÓXIMO CONTEXTO
```

Workflows antigos ou narrativos devem ser preservados, mas novos workflows devem seguir esse formato sempre que possível.

## 7. Regra de segurança contra alucinação operacional

REGRA:
A IA não deve transformar ausência de regra em permissão.

Quando não houver cobertura suficiente:

```text
Não inventar continuidade.
Não implementar por aproximação.
Não criar arquitetura por preferência.
Não registrar decisão como fato sem confirmação humana.
```

A ação correta é parar, registrar a lacuna e solicitar decisão.
