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

## 4. Regra de governança supervisionada da `.workbench`

Os arquivos da pasta `.workbench` são arquivos oficiais de governança do projeto.

Eles representam:

- estado oficial do projeto;
- workflow ativo;
- contexto persistente;
- histórico estrutural;
- estágio atual;
- decisões de engenharia.

Durante implementação:

```text
Agentes implementadores NÃO devem alterar silenciosamente os arquivos `.workbench`.
```

Fluxo obrigatório:

```text
Implementação
↓
Validação
↓
Relatório da etapa
↓
Sugestão explícita de atualização da governança
↓
Aprovação humana
↓
Atualização oficial da `.workbench`
```

Regra obrigatória:

```text
Toda alteração estrutural na `.workbench` deve ser:
- explícita;
- auditável;
- supervisionada;
- confirmada pelo supervisor humano.
```

Agentes implementadores podem:

```text
- sugerir alterações;
- gerar relatórios;
- propor atualização de etapa;
- propor atualização de CURRENT_STAGE.md;
- propor atualização de workflow.
```

Mas não devem:

```text
- consolidar silenciosamente governança;
- reescrever histórico do projeto;
- alterar workflow ativo sem autorização;
- alterar escopo oficialmente sem aprovação.
```

O objetivo desta regra é evitar:

- auto-governança silenciosa da IA;
- divergência entre implementação e estado oficial;
- perda de rastreabilidade;
- reescrita não supervisionada do histórico do projeto.

## 5. Regra de bootloader para repositório alvo

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

## 6. Regra de acesso ao repositório alvo

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

## 7. Criação inicial da pasta .workbench no projeto alvo

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

Regra obrigatória:

```text
Se a IA possuir permissão de escrita no repositório alvo, ela própria deve criar:

- a pasta `.workbench`;
- os arquivos iniciais;
- o conteúdo inicial desses arquivos;
- os commits iniciais relacionados à governança.
```

A IA não deve solicitar ao usuário que crie manualmente os arquivos `.workbench` quando a própria IA puder fazê-lo.

Somente quando a IA não possuir permissão de escrita ela poderá:

```text
- gerar comandos;
- orientar criação manual;
- solicitar intervenção humana.
```

## 8. Princípios invariáveis

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
- Nunca alterar silenciosamente arquivos oficiais de governança.

## 9. Fluxo universal

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
Relatório explícito da etapa
↓
Sugestão supervisionada de atualização da governança
↓
Aprovação humana
↓
Atualização oficial da `.workbench`
↓
Consolidação
```

## 10. Próximo passo após leitura

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
