# PROJECT ENGINEERING WORKFLOW TEMPLATE

Este template deve ser usado para criar o workflow local de engenharia do projeto alvo.

Destino recomendado no projeto alvo:

```text
.workbench/workflows/project-engineering/ENTRYPOINT.md
```

## 1. Propósito

Governar a transformação de uma ideia global em engenharia documentada, decomposição progressiva e tarefas atômicas prontas para futura geração de script de codação.

## 2. Contextos obrigatórios

Antes de executar este workflow local, a IA deve ler:

```text
1. .workbench/PROJECT_ENTRYPOINT.md
2. .workbench/PROJECT_WORKFLOW.md
3. .workbench/CURRENT_STAGE.md
4. AI_WORKBENCH/skills/governance-rules/SKILL.md
5. AI_WORKBENCH/docs/workbench-layered-responsibilities.md
```

## 3. Engenharia baseada em tecnologia

A engenharia do projeto deve ser especializada conforme a stack tecnológica registrada em:

```text
PROJECT_WORKFLOW.md
```

Campo esperado:

```text
PROJECT_TECHNOLOGIES:
```

Para cada tecnologia registrada, a IA deve:

```text
1. localizar o template tecnológico correspondente;
2. ler o template tecnológico;
3. incorporar suas regras na engenharia local;
4. adaptar a decomposição à tecnologia utilizada.
```

Exemplos:

```text
AI_WORKBENCH/templates/project-engineering/csharp-engineering-template.md
AI_WORKBENCH/templates/project-engineering/angular-engineering-template.md
AI_WORKBENCH/templates/project-engineering/arduino-engineering-template.md
```

## 4. Pastas de documentação obrigatórias

A IA deve validar:

```text
docs/requirements/
docs/architecture/
docs/decisions/
docs/validation/
```

Se ausentes, criar antes de continuar.

## 5. Ciclo progressivo de engenharia

A engenharia deve evoluir em ciclos:

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
↓
Pronto para script de codação
```

## 6. Regra de decomposição

A IA deve quebrar o escopo apenas até o nível necessário para eliminar ambiguidade técnica e permitir implementação segura.

A IA não deve gerar script de codação enquanto houver:

```text
- requisito ambíguo;
- decisão arquitetural pendente;
- contrato técnico indefinido;
- regra de validação ausente;
- dependência externa não mapeada;
- risco estrutural não registrado.
```

## 7. Definição de unidade atômica

Uma unidade atômica está pronta para virar script de codação quando possuir:

```text
- objetivo claro;
- escopo limitado;
- arquivos ou áreas afetadas definidos;
- regra de negócio ou regra técnica aprovada;
- contrato esperado;
- critérios de validação;
- limites explícitos do que NÃO fazer;
- dependências conhecidas;
- skill aplicável prevista;
- critério de conclusão.
```

## 8. Saídas documentais esperadas

A IA deve gerar ou atualizar documentação em:

```text
docs/requirements/
docs/architecture/
docs/decisions/
docs/validation/
```

A documentação deve ser suficiente para sustentar futura criação de:

```text
- skills locais;
- scripts de codação;
- critérios de validação;
- etapas de implementação.
```

## 9. Regra de parada

A IA deve parar quando a decomposição encontrar decisão arquitetural, ambiguidade crítica ou risco de inventar regra.

Ao parar, deve registrar:

```text
- lacuna encontrada;
- impacto;
- opções possíveis;
- decisão humana necessária;
- arquivo onde a decisão será registrada.
```

## 10. Próximo fluxo

Quando houver unidade atômica aprovada, o próximo fluxo será:

```text
AI_WORKBENCH/workflows/coding-script-generation/ENTRYPOINT.md
```

Se esse workflow ainda não existir, a IA deve parar e propor sua criação incremental.
