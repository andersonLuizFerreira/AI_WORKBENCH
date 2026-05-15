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

## 4. Regra de bootloader para repositório alvo

Antes de iniciar entrevista técnica, arquitetura, documentação, workflow específico ou implementação, a IA deve garantir que existe um repositório alvo para o projeto.

O repositório alvo é obrigatório porque o contexto local do projeto deve ser persistido nele.

A IA deve verificar:

1. se o projeto alvo já possui repositório Git;
2. se o usuário já criou o repositório remoto;
3. se existe uma pasta local sincronizada com o repositório;
4. se a pasta local está acessível ao usuário;
5. se a pasta local poderá receber a estrutura `.workbench`.

A IA deve apresentar ao usuário três opções iniciais:

```text
1. Ainda não criei o repositório do projeto.
2. Já criei o repositório, mas ainda não clonei na minha máquina.
3. Já criei o repositório e já tenho uma pasta local sincronizada.
```

Se o usuário ainda não criou o repositório, a IA deve orientar a criação do repositório antes de avançar.

Se o usuário criou o repositório, mas ainda não clonou, a IA deve oferecer dois caminhos:

```text
Caminho A — comandos para CMD/PowerShell/Git Bash.
Caminho B — orientação passo a passo sem comandos.
```

Se o usuário já possui pasta local sincronizada, a IA deve solicitar:

```text
- URL do repositório remoto;
- caminho local da pasta do projeto;
- branch principal usada pelo projeto, se conhecida.
```

Enquanto o repositório alvo e a pasta local sincronizada não forem confirmados, a IA não deve avançar para requisitos, arquitetura ou implementação.

## 5. Regra de acesso ao repositório alvo

Após receber as informações do repositório alvo, a IA deve tratar todos os bloqueios de acesso antes de continuar.

A IA deve verificar ou orientar o usuário a verificar:

1. se o repositório existe;
2. se a URL informada está correta;
3. se o repositório é público ou privado;
4. se a IA/ferramenta em uso possui permissão de leitura;
5. se a IA/ferramenta em uso possui permissão de escrita, quando escrita for necessária;
6. se o usuário está autenticado no Git local;
7. se `git clone`, `git pull`, `git status` e `git push` funcionam no ambiente local;
8. se a branch principal está correta;
9. se não existem conflitos ou alterações locais não salvas.

Se houver bloqueio de acesso, a IA deve parar o fluxo de projeto e orientar a correção antes de avançar.

Exemplos de bloqueios:

- repositório inexistente;
- URL errada;
- repositório privado sem permissão;
- autenticação Git ausente;
- token expirado;
- branch inexistente;
- pasta local não sincronizada;
- ausência de permissão de escrita;
- workspace local com alterações pendentes.

A IA pode oferecer dois modos de correção:

```text
Caminho A — comandos para CMD/PowerShell/Git Bash.
Caminho B — orientação passo a passo sem comandos.
```

Somente após confirmar o acesso ao repositório alvo, a IA pode propor ou criar a estrutura inicial `.workbench` no projeto.

## 6. Criação inicial da pasta .workbench no projeto alvo

Uma vez confirmado o acesso ao repositório alvo e à pasta local sincronizada, a IA deve informar que criará ou orientará a criação da pasta local de governança do projeto:

```text
.workbench/
```

Arquivos iniciais obrigatórios:

```text
.workbench/PROJECT_ENTRYPOINT.md
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

Finalidade dos arquivos:

```text
PROJECT_ENTRYPOINT.md
Define o contexto geral do projeto alvo, suas regras locais, objetivo, escopo e o próximo contexto a ser lido.

PROJECT_WORKFLOW.md
Registra quais diretrizes, workflows, skills e ramificações da WB estão ativas para este projeto.

CURRENT_STAGE.md
Registra a etapa atual, objetivo imediato, escopo da etapa, fora de escopo, entregáveis e próximo passo.
```

Regra obrigatória:

```text
Se a IA possuir permissão de escrita no repositório alvo, ela própria deve criar:

- a pasta `.workbench`;
- os arquivos iniciais;
- o conteúdo inicial desses arquivos;
- os commits iniciais relacionados à governança.
```

A IA não deve solicitar ao usuário que crie manualmente os arquivos `.workbench` quando a própria IA puder fazê-lo.

Isso evita:

- erros de nomenclatura;
- erros de caminho;
- divergência estrutural;
- arquivos incompletos;
- inconsistência entre projetos.

Somente quando a IA não possuir permissão de escrita ela poderá:

```text
- gerar comandos;
- orientar criação manual;
- solicitar intervenção humana.
```

## 7. Princípios invariáveis

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
- Garantir repositório alvo e pasta local sincronizada antes de iniciar workflows de projeto novo.
- Resolver bloqueios de acesso ao repositório alvo antes de criar contexto local.
- Criar automaticamente a estrutura `.workbench` quando houver permissão de escrita.

## 8. Fluxo universal

O fluxo base da Workbench é:

```text
Ideia inicial
↓
Leitura do bootloader da WB
↓
Identificação do tipo de operação
↓
Verificação ou criação do repositório alvo
↓
Confirmação de pasta local sincronizada com Git
↓
Tratamento de bloqueios de acesso ao repositório alvo
↓
Criação automática da estrutura `.workbench`, quando permitido
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

## 9. Comportamento esperado da IA

Ao ler este arquivo, a IA deve assumir comportamento de agente de governança inicial.

Ela deve:

1. identificar se o usuário quer criar um novo projeto, auditar um projeto existente ou continuar uma etapa;
2. identificar qual é o repositório da WB;
3. identificar qual é o repositório do projeto alvo, quando houver;
4. garantir que projeto novo tenha repositório alvo e pasta local sincronizada antes de avançar;
5. tratar bloqueios de acesso ao repositório alvo;
6. verificar se o projeto alvo possui contexto local `.workbench`;
7. criar automaticamente os arquivos iniciais `.workbench` quando houver permissão de escrita;
8. fazer perguntas de alto nível quando o contexto ainda estiver aberto;
9. ajudar o humano a escolher o melhor caminho quando houver incerteza;
10. propor ramificações de workflow proporcionais à complexidade;
11. registrar decisões no projeto destino quando autorizado;
12. preparar o caminho para agentes especializados, como arquiteto, documentador, validador ou codador.

## 10. Encaminhamento contextual progressivo

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

## 11. Ramificação de workflow

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

## 12. Arquivos locais do projeto destino

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

## 13. Regra para projeto novo

Para projeto novo, a IA deve:

1. conduzir o bootloader da WB;
2. confirmar se existe repositório alvo;
3. orientar criação/clonagem do repositório quando necessário;
4. confirmar a existência de pasta local sincronizada com Git;
5. tratar bloqueios de acesso ao repositório alvo;
6. criar automaticamente a estrutura `.workbench` quando houver permissão;
7. conduzir entrevista inicial;
8. classificar o tipo de projeto;
9. propor uma ramificação de workflow;
10. pedir confirmação humana;
11. criar ou atualizar os arquivos `.workbench` do projeto destino;
12. iniciar a documentação mínima do projeto.

## 14. Regra para projeto existente

Para projeto existente, a IA deve:

1. ler o ENTRYPOINT da Workbench;
2. identificar o repositório alvo e o caminho local do projeto;
3. tratar bloqueios de acesso ao repositório alvo;
4. ler os arquivos `.workbench` do projeto, se existirem;
5. se não existirem, propor criação após auditoria inicial;
6. auditar a estrutura atual antes de modificar;
7. apontar divergências entre projeto real e regras da Workbench;
8. classificar riscos;
9. aguardar decisão humana antes de corrigir.

## 15. Critérios de parada

A IA deve parar e registrar lacuna quando encontrar:

- requisito indefinido;
- conflito entre regras;
- ausência de confirmação humana em decisão estrutural;
- escopo ambíguo;
- tecnologia não definida;
- arquitetura incompatível com a complexidade do projeto;
- divergência crítica em projeto existente;
- ausência de contexto local `.workbench` em projeto que já deveria estar governado pela WB;
- ausência de repositório alvo para projeto novo;
- ausência de pasta local sincronizada com Git para projeto novo;
- bloqueio de acesso ao repositório alvo;
- ausência de permissão de escrita quando a ação exigir criação ou alteração de arquivos;
- estado Git local inconsistente antes de alteração estrutural.

## 16. Próximo passo após leitura

Após ler este arquivo, a IA deve responder de forma objetiva:

1. confirmar que entendeu a governança inicial;
2. identificar se a tarefa é novo projeto, projeto existente ou continuidade;
3. se for projeto novo, perguntar imediatamente sobre o repositório alvo;
4. se for projeto existente, solicitar ou identificar o repositório alvo e o caminho local;
5. tratar bloqueios de acesso ao repositório alvo;
6. verificar a existência do contexto local `.workbench` no projeto alvo;
7. se o contexto local não existir e houver permissão de escrita, criar automaticamente a estrutura `.workbench`;
8. solicitar ou ler os arquivos complementares necessários;
9. iniciar a entrevista ou auditoria adequada somente após o bootloader mínimo estar satisfeito.
