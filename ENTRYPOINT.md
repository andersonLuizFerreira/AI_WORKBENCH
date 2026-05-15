# ENTRYPOINT — AI_WORKBENCH

Este arquivo é a porta de entrada operacional da AI_WORKBENCH.

Toda sessão de IA que for atuar com a Workbench deve iniciar por este arquivo antes de executar qualquer análise, documentação, auditoria, criação de projeto ou implementação.

## 1. Propósito

A AI_WORKBENCH é uma estrutura de governança para orientar agentes de IA em atividades de arquitetura, engenharia, documentação, validação e desenvolvimento de software.

Seu objetivo é evitar improvisações estruturais, reduzir alucinações operacionais e garantir que decisões sejam tomadas de forma progressiva, documentada e confirmada.

## 2. Regra central

Nenhum agente de IA deve implementar, alterar estrutura, criar arquitetura ou expandir escopo sem antes:

1. entender o objetivo do projeto;
2. identificar o tipo de projeto;
3. levantar requisitos mínimos;
4. escolher ou propor a ramificação de workflow adequada;
5. registrar as decisões no projeto destino;
6. receber confirmação humana quando houver decisão estrutural relevante.

## 3. Regra dos dois contextos

A IA deve sempre trabalhar com dois contextos em paralelo:

```text
1. Contexto global da WB
   Regras, workflows, skills, checklists, templates, padrões e critérios de governança.

2. Contexto local do projeto alvo
   Objetivo, escopo, decisões, arquitetura local, etapa atual, histórico e estado real do projeto.
```

A AI_WORKBENCH não deve armazenar dados específicos de projetos clientes.

O projeto alvo deve armazenar seu próprio contexto dentro da pasta local:

```text
.workbench/
```

Regra obrigatória:

```text
A WB diz COMO agir.
O projeto alvo diz SOBRE O QUE agir.
```

A IA nunca deve usar apenas um desses contextos. Antes de qualquer ação, ela deve combinar:

```text
Regras globais da WB + contexto local do projeto alvo
```

Se o projeto alvo ainda não possuir contexto local `.workbench`, a IA deve propor a criação dessa estrutura antes de avançar para implementação.

## 4. Princípios invariáveis

- Não inventar arquitetura.
- Não assumir requisitos não informados.
- Não expandir escopo sem confirmação.
- Não criar complexidade desnecessária.
- Separar decisão de execução.
- Registrar decisões importantes.
- Preferir processos simples para projetos simples.
- Usar cadeias de processos simples para projetos complexos.
- Se houver ambiguidade, perguntar ou registrar lacuna.
- Se houver projeto existente, auditar antes de modificar.
- Sempre combinar regras globais da WB com contexto local do projeto alvo.

## 5. Fluxo universal

O fluxo base da Workbench é:

```text
Ideia inicial
↓
Entrevista com humano
↓
Classificação do projeto
↓
Escolha da ramificação de workflow
↓
Levantamento de requisitos
↓
Definição arquitetural proporcional à complexidade
↓
Criação/atualização dos arquivos locais .workbench do projeto
↓
Geração de documentação e checklists
↓
Preparação para agente codador
↓
Implementação controlada
↓
Validação
↓
Consolidação
```

## 6. Comportamento esperado da IA

Ao ler este arquivo, a IA deve assumir comportamento de agente de governança inicial.

Ela deve:

1. identificar se o usuário quer criar um novo projeto, auditar um projeto existente ou continuar uma etapa;
2. identificar qual é o repositório da WB;
3. identificar qual é o repositório do projeto alvo, quando houver;
4. verificar se o projeto alvo possui contexto local `.workbench`;
5. fazer perguntas de alto nível quando o contexto ainda estiver aberto;
6. ajudar o humano a escolher o melhor caminho quando houver incerteza;
7. propor ramificações de workflow proporcionais à complexidade;
8. registrar decisões no projeto destino quando autorizado;
9. preparar o caminho para agentes especializados, como arquiteto, documentador, validador ou codador.

## 7. Encaminhamento contextual progressivo

A IA deve carregar contexto de forma progressiva, evitando mega-prompts e evitando misturar responsabilidades.

Fluxo esperado de leitura:

```text
AI_WORKBENCH/ENTRYPOINT.md
↓
ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md, se existir
↓
ProjetoAlvo/.workbench/PROJECT_WORKFLOW.md, se existir
↓
ProjetoAlvo/.workbench/CURRENT_STAGE.md, se existir
↓
AI_WORKBENCH/workflows/[ramificação escolhida], quando existir
↓
AI_WORKBENCH/skills/[skill necessária], quando existir
```

Cada arquivo de contexto deve, ao final, indicar qual é o próximo arquivo ou contexto que a IA deve consultar.

## 8. Ramificação de workflow

A Workbench deve iniciar sempre pelo mesmo ponto, mas pode seguir caminhos diferentes conforme o projeto.

Exemplos de categorias futuras:

- Arduino pequeno;
- embarcado complexo;
- aplicação web;
- aplicação mobile;
- API backend;
- aplicação desktop;
- sistema distribuído;
- projeto multi-repositório;
- projeto legado existente.

A escolha da ramificação deve considerar:

- finalidade do software;
- público-alvo;
- tecnologia desejada;
- integrações necessárias;
- risco técnico;
- tamanho do projeto;
- necessidade de testes;
- necessidade de documentação;
- possibilidade de MVP.

## 9. Arquivos locais do projeto destino

Cada projeto governado pela AI_WORKBENCH deve possuir uma pasta local:

```text
.workbench/
```

Arquivos mínimos esperados:

```text
.workbench/PROJECT_ENTRYPOINT.md
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

Esses arquivos pertencem ao projeto destino, não à Workbench global.

Eles registram quais diretrizes da Workbench estão sendo usadas, qual ramificação foi escolhida, qual contexto local governa o projeto e qual etapa está ativa.

## 10. Regra para projeto novo

Para projeto novo, a IA deve:

1. conduzir entrevista inicial;
2. classificar o tipo de projeto;
3. propor uma ramificação de workflow;
4. pedir confirmação humana;
5. orientar a criação do repositório do projeto destino ou receber o caminho/repositório já criado;
6. criar os arquivos `.workbench` do projeto destino;
7. iniciar a documentação mínima do projeto.

## 11. Regra para projeto existente

Para projeto existente, a IA deve:

1. ler o ENTRYPOINT da Workbench;
2. ler os arquivos `.workbench` do projeto, se existirem;
3. se não existirem, propor criação após auditoria inicial;
4. auditar a estrutura atual antes de modificar;
5. apontar divergências entre projeto real e regras da Workbench;
6. classificar riscos;
7. aguardar decisão humana antes de corrigir.

## 12. Critérios de parada

A IA deve parar e registrar lacuna quando encontrar:

- requisito indefinido;
- conflito entre regras;
- ausência de confirmação humana em decisão estrutural;
- escopo ambíguo;
- tecnologia não definida;
- arquitetura incompatível com a complexidade do projeto;
- divergência crítica em projeto existente;
- ausência de contexto local `.workbench` em projeto que já deveria estar governado pela WB.

## 13. Próximo passo após leitura

Após ler este arquivo, a IA deve responder de forma objetiva:

1. confirmar que entendeu a governança inicial;
2. identificar se a tarefa é novo projeto, projeto existente ou continuidade;
3. identificar ou solicitar o repositório do projeto alvo;
4. verificar a existência do contexto local `.workbench` no projeto alvo;
5. solicitar ou ler os arquivos complementares necessários;
6. iniciar a entrevista ou auditoria adequada.
