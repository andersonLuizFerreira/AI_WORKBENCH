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

## 4. Regra de separação entre bootstrap e entrevista

O bootloader da WB NÃO deve misturar:

```text
- criação estrutural do projeto
com
- levantamento de requisitos funcionais.
```

A criação do repositório, da pasta local e da estrutura `.workbench` deve acontecer antes da entrevista detalhada do projeto.

Durante o bootstrap, a IA NÃO deve exigir informações como:

```text
- funcionalidades detalhadas;
- arquitetura do sistema;
- plataforma final;
- regras de negócio;
- persistência;
- público alvo;
- complexidade funcional;
- requisitos avançados.
```

Essas informações pertencem à etapa posterior:

```text
Entrevista inicial do projeto
```

## 5. Informações mínimas obrigatórias para bootstrap

Para executar o bootstrap inicial do projeto, a IA deve solicitar apenas:

```text
1. Nome do projeto
2. URL do repositório remoto
3. Caminho local da pasta do projeto
4. Branch principal, se conhecida
```

Com essas informações, a IA já deve ser capaz de:

```text
- validar o repositório;
- validar Git local;
- validar sincronização;
- criar a estrutura `.workbench`;
- registrar contexto mínimo inicial.
```

## 6. Contexto mínimo inicial do projeto

Após o bootstrap, mas antes da entrevista funcional, os arquivos `.workbench` devem conter apenas contexto mínimo.

Exemplo esperado:

```text
PROJECT_ENTRYPOINT.md
- nome do projeto
- repositório
- branch
- caminho local
- status: aguardando entrevista inicial

PROJECT_WORKFLOW.md
- workflow: não definido
- ramificação: pendente
- status: aguardando classificação

CURRENT_STAGE.md
- etapa atual: bootstrap concluído
- próxima etapa: entrevista inicial
```

A IA não deve inventar requisitos funcionais antes da entrevista do projeto.

## 7. Regra de governança supervisionada da `.workbench`

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

## 8. Regra de bootloader para repositório alvo

Antes de iniciar entrevista técnica, arquitetura, documentação, workflow específico ou implementação, a IA deve garantir que existe um repositório alvo para o projeto.

O repositório alvo é obrigatório porque o contexto local do projeto deve ser persistido nele.

A IA deve verificar:

1. se o projeto alvo já possui repositório Git;
2. se o usuário já criou o repositório remoto;
3. se existe uma pasta local sincronizada com o repositório;
4. se a pasta local está acessível ao usuário;
5. se a pasta local poderá receber a estrutura `.workbench`.

## 9. Regra de acesso ao repositório alvo

Após receber as informações do repositório alvo, a IA deve tratar todos os bloqueios de acesso antes de continuar.

A IA deve verificar ou orientar o usuário a verificar:

1. se o repositório existe;
2. se a URL informada está correta;
3. se o repositório é público ou privado;
4. se a IA/ferramenta em uso possui permissão de leitura;
5. se a IA/ferramenta em uso possui permissão de escrita;
6. se o usuário está autenticado no Git local;
7. se `git clone`, `git pull`, `git status` e `git push` funcionam;
8. se a branch principal está correta.

## 10. Criação inicial da pasta .workbench no projeto alvo

Uma vez confirmado o acesso ao repositório alvo e à pasta local sincronizada, a IA deve criar automaticamente:

```text
.workbench/
```

Arquivos iniciais obrigatórios:

```text
.workbench/PROJECT_ENTRYPOINT.md
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

Se a IA possuir permissão de escrita, ela própria deve:

```text
- criar a pasta `.workbench`;
- criar os arquivos iniciais;
- preencher conteúdo mínimo inicial;
- registrar commits iniciais de governança.
```

## 11. Biblioteca de workflows da WB

A WB deve possuir uma biblioteca de definições para diferentes tipos de projeto.

Essas definições vivem dentro do repositório da WB, não dentro dos projetos clientes.

Exemplos de caminhos futuros:

```text
workflows/project-classification/
workflows/simple-projects/
workflows/medium-projects/
workflows/complex-projects/
workflows/web-projects/
workflows/api-projects/
workflows/desktop-projects/
workflows/embedded-projects/
workflows/mobile-projects/
```

O projeto alvo deve armazenar apenas qual caminho da WB está sendo usado e quais decisões locais foram tomadas.

## 12. Regra de cobertura do contexto local

As regras do projeto alvo registradas em `.workbench` são verdadeiras enquanto estiverem dentro da cobertura daquele contexto.

Se a IA encontrar uma situação não coberta pelo contexto local, ela deve:

```text
1. parar;
2. registrar a lacuna;
3. consultar a biblioteca de workflows da WB;
4. orientar-se com o operador humano;
5. escolher ou confirmar o próximo caminho;
6. registrar a nova decisão no `.workbench` local, com aprovação explícita.
```

A IA não deve inventar continuidade quando a cobertura local acabar.

## 13. Encaminhamento após bootstrap

Ao concluir o bootstrap e criar o contexto mínimo inicial, a IA deve encaminhar o fluxo para a classificação do projeto.

Próximo arquivo obrigatório na WB:

```text
workflows/project-classification/ENTRYPOINT.md
```

A IA deve então:

```text
1. ler o PROJECT_ENTRYPOINT.md do projeto alvo;
2. ler o PROJECT_WORKFLOW.md do projeto alvo;
3. ler o CURRENT_STAGE.md do projeto alvo;
4. ler workflows/project-classification/ENTRYPOINT.md da WB;
5. classificar complexidade, tecnologias, plataformas e agente implementador;
6. propor o próximo caminho da biblioteca WB;
7. solicitar confirmação humana;
8. registrar a ramificação escolhida no PROJECT_WORKFLOW.md do projeto alvo.
```

## 14. Fluxo universal

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
Tratamento de bloqueios de acesso
↓
Criação automática da `.workbench`
↓
Registro do contexto mínimo inicial
↓
Bootstrap concluído
↓
Leitura do contexto local do projeto
↓
Classificação do projeto via workflows/project-classification/
↓
Escolha da ramificação de workflow
↓
Registro supervisionado da ramificação no projeto alvo
↓
Entrevista inicial direcionada
↓
Levantamento de requisitos
↓
Definição arquitetural proporcional
↓
Implementação controlada
↓
Validação
↓
Governança supervisionada
↓
Consolidação
```

## 15. Próximo passo após leitura

Após ler este arquivo, a IA deve:

```text
1. identificar o tipo de operação;
2. solicitar apenas os dados mínimos do bootstrap;
3. validar repositório e Git local;
4. criar automaticamente a estrutura `.workbench`, quando permitido;
5. registrar contexto mínimo inicial;
6. concluir o bootstrap;
7. ler o contexto local do projeto;
8. encaminhar o fluxo para workflows/project-classification/ENTRYPOINT.md.
```
