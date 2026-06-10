# Índice de Arquivos do Projeto

## Objetivo

Este documento funciona como índice navegável dos arquivos importantes da AI_WORKBENCH.

A AI_WORKBENCH não é um projeto de negócio específico. Ela é um repositório de padronização para orientar projetos futuros no uso de IA durante descoberta, arquitetura, engenharia, planejamento, execução, validação e consolidação.

O objetivo deste índice é ajudar humanos e agentes de IA a localizar rapidamente as fontes oficiais do projeto, reduzindo buscas repetidas, leitura incompleta e decisões baseadas em contexto parcial.

## Como usar este índice

Antes de executar uma tarefa relevante neste repositório, consulte primeiro as seções abaixo para identificar:

- qual arquivo define o ponto de entrada operacional;
- onde estão as regras de governança;
- onde estão os workflows oficiais;
- quais templates devem ser usados em projetos alvo;
- quais documentos explicam responsabilidades e limites;
- quais estruturas ainda são apenas recomendadas e não existem neste repositório.

Depois de localizar os arquivos aplicáveis, leia os documentos oficiais na ordem indicada pelo fluxo operacional.

## Arquivos principais

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `README.md` | Apresentação pública da AI_WORKBENCH, objetivos, filosofia e visão geral em múltiplos idiomas. | Consultar para entender o propósito geral do repositório. | Não é o ponto operacional principal para agentes de IA; ele encaminha para `ENTRYPOINT.md`. |
| `ENTRYPOINT.md` | Porta de entrada operacional global da AI_WORKBENCH. Define bootloader, regras centrais, separação entre contexto global e contexto local, bootstrap e fluxo universal. | Consultar no início de qualquer sessão de IA ou quando faltar orientação global. | Arquivo operacional mais importante do repositório. Deve ser lido antes de workflows, templates ou skills. |
| `.workbench/PROJECT_WORKFLOW.md` | Registra o workflow atual da própria AI_WORKBENCH, sua estratégia de crescimento e regras arquiteturais principais. | Consultar ao alterar ou expandir a Workbench. | Representa contexto local de governança deste repositório. |
| `.workbench/CURRENT_STAGE.md` | Registra a etapa atual da AI_WORKBENCH, escopo, limites e próximas etapas sugeridas. | Consultar antes de criar novas estruturas, workflows, skills ou documentos. | Ajuda a evitar expansão fora da etapa atual. |
| `docs/workbench-layered-responsibilities.md` | Define as camadas conceituais da Workbench: governança, bootstrap, engenharia, documentação, skills, scripts, validação e consolidação. | Consultar ao decidir onde uma nova regra, template, workflow ou documento deve ficar. | Documento-chave para evitar mistura de responsabilidades. |

## Pastas principais

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `.workbench/` | Guarda o estado operacional local da própria AI_WORKBENCH. | Consultar para entender a etapa atual e o workflow local do repositório. | Não deve ser alterada silenciosamente por agentes implementadores. |
| `docs/` | Guarda documentação oficial, conceitual, arquitetural e de governança da Workbench. | Consultar para entender responsabilidades, arquitetura documental e decisões globais. | Neste momento contém documentação conceitual e este índice de governança. |
| `docs/00-governanca/` | Guarda documentos de governança e navegação estrutural do repositório. | Consultar para localizar índices, regras globais e documentos orientadores de alto nível. | Criada para organizar este índice e futuros documentos de governança. |
| `skills/` | Guarda skills globais usadas por agentes de IA. | Consultar quando a tarefa exigir comportamento operacional padronizado. | Atualmente contém a skill de regras de governança. |
| `templates/` | Guarda modelos oficiais para criar arquivos de governança e engenharia em projetos alvo. | Consultar durante bootstrap, classificação ou criação de workflows locais. | Templates não devem ser usados como contexto final sem preencher placeholders. |
| `templates/project-engineering/` | Guarda templates de engenharia especializados por tecnologia. | Consultar quando um projeto alvo declarar tecnologia específica como C#, Angular ou Arduino. | Serve para especializar a engenharia antes da codificação. |
| `workflows/` | Guarda workflows globais da AI_WORKBENCH. | Consultar ao escolher ou executar uma etapa operacional da Workbench. | Cada workflow possui seu próprio `ENTRYPOINT.md`. |
| `workflows/project-adoption/` | Guarda o fluxo de adoção gradual da Workbench em projetos existentes sem `.workbench`. | Consultar quando um projeto legado ou existente ainda não tiver contexto local da Workbench. | Evita reestruturação agressiva sem inventário e aprovação. |
| `workflows/project-bootstrap/` | Guarda o fluxo de criação ou validação inicial de projetos alvo. | Consultar antes de criar `.workbench`, docs mínimos ou fundação de projeto. | Define estrutura universal obrigatória para projetos governados. |
| `workflows/project-classification/` | Guarda o fluxo de classificação de projetos após bootstrap. | Consultar para definir complexidade, tipo de aplicação, stack, autonomia e workflow recomendado. | A IA deve classificar antes de escolher workflow especializado. |
| `workflows/project-engineering/` | Guarda o fluxo global de engenharia e arquitetura de projetos. | Consultar após bootstrap e classificação, antes de qualquer codificação. | Define que engenharia deve documentar antes de liberar script de codação. |

## Arquivos de governança

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `ENTRYPOINT.md` | Define regras globais, bootloader, fluxo universal e separação entre contexto global e local. | Início de sessão, criação de projeto alvo, auditoria ou dúvida operacional. | Fonte operacional global primária. |
| `.workbench/PROJECT_WORKFLOW.md` | Define o estado de workflow da AI_WORKBENCH e sua estratégia incremental. | Antes de expandir a Workbench. | Deve orientar crescimento modular e sem dados de projetos clientes. |
| `.workbench/CURRENT_STAGE.md` | Define etapa atual, escopo permitido e limites da Workbench. | Antes de criar documentos, workflows, skills ou templates novos. | O estado atual está em construção e tem limites explícitos. |
| `docs/00-governanca/indice-arquivos-projeto.md` | Índice navegável dos arquivos importantes do projeto. | Antes de qualquer tarefa relevante no repositório. | Deve ser mantido atualizado quando a estrutura mudar. |
| `skills/governance-rules/SKILL.md` | Define regras transversais de governança, parada, autonomia, exceções e segurança contra alucinação operacional. | Sempre que houver bootstrap, classificação, documentação, auditoria, implementação controlada ou atualização de `.workbench`. | Skill global obrigatória para comportamento disciplinado de IA. |

## Arquivos de agentes

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `skills/governance-rules/SKILL.md` | Orienta o comportamento operacional de agentes de IA em decisões, paradas, autonomia e governança. | Consultar quando a IA precisar saber o que pode fazer, quando parar e quando pedir aprovação humana. | Atualmente é o principal arquivo de agente existente no repositório. |

## Arquivos de arquitetura

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `docs/workbench-layered-responsibilities.md` | Explica a arquitetura conceitual por camadas da Workbench. | Consultar antes de decidir onde colocar regras, documentação, skills, workflows, scripts ou validações. | Ajuda a preservar separação entre engenharia, execução e consolidação. |
| `templates/project-engineering/csharp-engineering-template.md` | Template de engenharia para projetos C# e .NET. | Consultar quando um projeto alvo usar C#, .NET, WinForms, WPF, backend ou biblioteca C#. | Define pontos que devem existir na documentação de arquitetura do projeto alvo antes da codificação. |
| `templates/project-engineering/angular-engineering-template.md` | Template de engenharia para projetos Angular e TypeScript frontend. | Consultar quando um projeto alvo usar Angular, SPA, Angular Material ou frontend modular. | Define módulos, serviços, estado, roteamento e contratos com APIs. |
| `templates/project-engineering/arduino-engineering-template.md` | Template de engenharia para Arduino, ESP32 e sistemas embarcados. | Consultar quando um projeto alvo envolver firmware, GPIO, protocolos, timers ou interrupções. | Reforça requisitos temporais, hardware e validação de sinais. |

## Arquivos de especificação e execução

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `workflows/project-bootstrap/ENTRYPOINT.md` | Especifica o workflow de bootstrap de projetos alvo. | Consultar ao iniciar projeto novo, validar repositório, criar `.workbench` local ou docs mínimos. | Define sequência fixa inicial e estrutura universal obrigatória. |
| `workflows/project-classification/ENTRYPOINT.md` | Especifica o workflow de classificação de projetos. | Consultar após bootstrap para classificar complexidade, aplicação, tecnologias, plataformas e autonomia. | Deve preceder workflows especializados. |
| `workflows/project-adoption/ENTRYPOINT.md` | Especifica como adequar projetos existentes à Workbench. | Consultar quando um projeto existente não possuir `.workbench`. | Requer inventário e aprovação antes de criar governança local. |
| `workflows/project-engineering/ENTRYPOINT.md` | Especifica a etapa de engenharia e arquitetura. | Consultar quando o projeto já tem bootstrap concluído e precisa transformar ideia em engenharia documentada. | Não permite implementação de produto durante engenharia. |
| `templates/project-entrypoint-template.md` | Modelo para criar o PROJECT_ENTRYPOINT local em projetos alvo. | Consultar durante bootstrap de projeto alvo. | Deve ser preenchido com dados reais; placeholders não são contexto válido. |
| `templates/project-workflow-template.md` | Modelo para criar o PROJECT_WORKFLOW local em projetos alvo. | Consultar durante bootstrap ou classificação de projeto alvo. | Contém campos de workflow, tecnologia, autonomia e roteamento. |
| `templates/current-stage-template.md` | Modelo para criar o CURRENT_STAGE local em projetos alvo. | Consultar durante bootstrap e consolidação de etapa. | Deve registrar estágio, bloqueios, referências, validação e próxima ação. |
| `templates/project-engineering-workflow-template.md` | Modelo para criar workflow local de engenharia em projetos alvo. | Consultar quando a etapa atual exigir engenharia e arquitetura local. | O destino recomendado fica dentro da pasta de workflows locais do projeto alvo. |

## Arquivos de prompts

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `templates/` | Contém modelos que podem orientar prompts operacionais e geração de arquivos locais em projetos alvo. | Consultar quando a IA precisar criar contexto local padronizado ou workflow derivado. | Não há pasta de prompts no estado atual do repositório. |

## Arquivos de fluxo de trabalho

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `workflows/project-bootstrap/ENTRYPOINT.md` | Fluxo inicial de criação, validação e preparação de projeto alvo. | Antes de qualquer entrevista técnica ou implementação. | Primeiro workflow operacional após o bootloader global. |
| `workflows/project-classification/ENTRYPOINT.md` | Fluxo para definir complexidade, tipo de projeto, tecnologias e autonomia. | Depois do bootstrap e antes de especializações. | Registra lacunas e workflows inexistentes quando necessário. |
| `workflows/project-adoption/ENTRYPOINT.md` | Fluxo para adoção da Workbench em projetos existentes. | Quando não houver `.workbench` local em projeto legado. | Prioriza inventário, diagnóstico e adoção gradual. |
| `workflows/project-engineering/ENTRYPOINT.md` | Fluxo para transformar ideia em engenharia documentada. | Após bootstrap e classificação, antes de scripts de codação. | Usa as pastas de requisitos, arquitetura, decisões e validação do projeto alvo. |

## Arquivos de validação

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `skills/governance-rules/SKILL.md` | Define critérios de parada, bloqueios e validações operacionais da IA. | Consultar antes de tomar decisões com risco de ambiguidade, alucinação operacional ou alteração estrutural. | Validação aqui é governança de comportamento, não teste automatizado. |
| `workflows/project-bootstrap/ENTRYPOINT.md` | Define validações de repositório, Git, estrutura universal e documentação mínima. | Consultar durante criação ou adequação inicial de projeto alvo. | Inclui validações de pastas obrigatórias. |
| `workflows/project-engineering/ENTRYPOINT.md` | Define bloqueios e critérios para considerar engenharia suficientemente documentada. | Consultar antes de liberar futura codificação. | Bloqueia script de codação quando há arquitetura ou requisito indefinido. |
| `templates/project-engineering/csharp-engineering-template.md` | Define validações esperadas para engenharia C#. | Consultar antes de liberar codificação C#. | Exige namespaces, dependências, build e testes definidos. |
| `templates/project-engineering/angular-engineering-template.md` | Define validações esperadas para engenharia Angular. | Consultar antes de liberar codificação Angular. | Exige módulos, responsabilidades, contratos de API e critérios de teste. |
| `templates/project-engineering/arduino-engineering-template.md` | Define validações esperadas para engenharia embarcada. | Consultar antes de liberar codificação Arduino ou ESP32. | Exige módulos, contratos de comunicação, requisitos temporais e riscos de hardware. |

## Arquivos de relatórios

| Caminho | Finalidade | Quando consultar | Observações |
|---|---|---|---|
| `.workbench/CURRENT_STAGE.md` | Registra estado atual, bloqueios, validações e próximas ações da própria AI_WORKBENCH. | Consultar como relatório operacional mínimo da etapa atual. | Não há pasta específica de relatórios no estado atual do repositório. |

## Arquivos recomendados ainda não existentes

Os caminhos abaixo são recomendações futuras. Eles não devem ser tratados como existentes no estado atual do repositório.

| Caminho recomendado | Finalidade | Quando criar | Observações |
|---|---|---|---|
| `.agents/` | Guardar definições formais de agentes, papéis, permissões e responsabilidades. | Criar quando a Workbench passar a operar com agentes especializados. | O pedido original cita `.agents/`, mas a pasta ainda não existe neste repositório. |
| `checklists/` | Guardar checklists oficiais de validação, execução e revisão por etapa. | Criar quando houver critérios recorrentes que precisem ser executados por humanos ou IA. | Citada na visão inicial do README, mas ainda ausente. |
| `prompts/` | Guardar prompts oficiais versionados para agentes e etapas específicas. | Criar quando prompts deixarem de ser instruções ocasionais e virarem contratos reutilizáveis. | Atualmente templates cumprem parte desse papel. |
| `validations/` | Guardar validações formais, evidências e critérios reutilizáveis. | Criar quando a Workbench precisar separar validações globais de workflows e skills. | Citada na estrutura inicial do README, mas ainda ausente. |
| `reports/` | Guardar relatórios consolidados de auditoria, validação e execução da própria Workbench. | Criar quando houver relatórios recorrentes fora de `.workbench/CURRENT_STAGE.md`. | Deve evitar duplicar responsabilidades de `docs/validation/` em projetos alvo. |
| `docs/architecture/` | Guardar arquitetura formal da própria AI_WORKBENCH. | Criar quando houver decisões arquiteturais internas mais detalhadas que o documento de responsabilidades em camadas. | Hoje a arquitetura conceitual está em `docs/workbench-layered-responsibilities.md`. |
| `docs/decisions/` | Guardar ADRs e decisões de governança ou arquitetura da própria AI_WORKBENCH. | Criar quando decisões passarem a exigir histórico formal. | Não confundir com `docs/decisions/` de projetos alvo. |
| `docs/validation/` | Guardar documentação de validação da própria AI_WORKBENCH. | Criar quando houver critérios oficiais de validação global da Workbench. | Não existe atualmente na Workbench, embora seja exigida em projetos alvo. |
| `workflows/coding-script-generation/ENTRYPOINT.md` | Definir o workflow futuro de geração de scripts de codação. | Criar quando houver engenharia suficiente para transformar unidades atômicas em contratos de implementação. | Já é citado como próximo fluxo futuro nos workflows de engenharia. |

## Regras para manutenção deste índice

Este índice deve ser atualizado sempre que:

- uma nova pasta estrutural for criada;
- um novo documento de governança for criado;
- um novo agente for adicionado;
- uma nova regra operacional for definida;
- um novo workflow for incluído;
- uma nova skill global for adicionada;
- um novo template oficial for criado;
- um arquivo mudar de responsabilidade;
- um arquivo deixar de existir.

Regras de manutenção:

- Não listar arquivos inexistentes fora da seção `Arquivos recomendados ainda não existentes`.
- Usar caminhos relativos à raiz do repositório.
- Manter descrições objetivas e orientadas ao uso por humanos e agentes de IA.
- Indicar claramente quando um arquivo é fonte oficial, template, workflow, skill ou recomendação futura.
- Revisar este índice após mudanças estruturais antes de considerar a tarefa concluída.

## Regra operacional para IA

Antes de executar qualquer tarefa relevante neste repositório, a IA deve consultar este índice para localizar os arquivos oficiais do projeto e evitar buscas repetidas, leitura incompleta ou decisões baseadas em contexto parcial.
