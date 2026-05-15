# ENTRYPOINT — Project Classification Workflow

Este arquivo define o primeiro workflow após o bootstrap da AI_WORKBENCH.

Ele deve ser lido depois que a IA concluir o bootstrap, validar o repositório alvo e criar ou ler a pasta `.workbench` do projeto.

## 1. Propósito

Classificar o projeto antes de escolher a próxima ramificação da WB.

A IA deve decidir o caminho com base em:

- complexidade da aplicação;
- tipo de aplicação;
- tecnologias envolvidas;
- plataformas usadas;
- agente ou ferramenta que fará a implementação;
- nível de documentação necessário;
- estrutura mínima de pastas recomendada;
- autonomia local desejada para o projeto.

## 2. Regra central

A IA deve classificar antes de especializar.

```text
Não escolher workflow especializado antes de classificar o projeto.
Não escolher arquitetura antes de entender complexidade e contexto.
Não aplicar estrutura pesada em projeto simples.
Não aplicar estrutura simples em projeto que exige organização maior.
```

## 3. Arquivos que devem ser lidos antes deste workflow

```text
1. AI_WORKBENCH/ENTRYPOINT.md
2. AI_WORKBENCH/skills/governance-rules/SKILL.md
3. ProjetoAlvo/.workbench/PROJECT_ENTRYPOINT.md
4. ProjetoAlvo/.workbench/PROJECT_WORKFLOW.md
5. ProjetoAlvo/.workbench/CURRENT_STAGE.md
```

Se algum desses arquivos estiver ausente, a IA deve retornar ao bootstrap.

## 4. Classificação de complexidade

A IA deve classificar o projeto em uma das categorias:

```text
1. Simples
2. Médio
3. Complexo
```

Critérios resumidos:

```text
Simples:
- poucas funções;
- baixa quantidade de arquivos;
- baixa necessidade de documentação;
- pouca ou nenhuma integração externa.

Médio:
- vários módulos ou telas;
- alguma separação de responsabilidades;
- algum uso de persistência ou integração;
- documentação moderada.

Complexo:
- múltiplos módulos ou tecnologias;
- integrações importantes;
- necessidade de arquitetura formal;
- documentação e validação mais rigorosas.
```

## 5. Tipo de aplicação

A IA deve identificar o tipo principal:

```text
- Desktop
- Console
- Web
- Mobile
- API Backend
- Embarcado
- Banco de dados
- Sistema multi-tecnologia
- Biblioteca/SDK
- Automação/script
- Outro
```

## 6. Tecnologias envolvidas

A IA deve registrar as tecnologias conhecidas.

Exemplos:

```text
- C#
- .NET Framework
- .NET moderno
- JavaScript/TypeScript
- Angular
- React
- Node.js
- Python
- Arduino
- ESP32
- SQL
- NoSQL
- Outro
```

Se o usuário não souber a tecnologia, a IA deve ajudar a comparar opções antes de registrar a decisão.

## 7. Plataformas usadas

A IA deve registrar as plataformas envolvidas:

```text
- Windows
- Linux
- Web browser
- Android
- iOS
- Microcontrolador
- Servidor local
- Cloud
- Multi-plataforma
```

## 8. Agente implementador

A IA deve registrar quem provavelmente implementará o projeto:

```text
- Codex
- ChatGPT orientando humano
- Cursor
- Claude Code
- Copilot
- Humano
- Misto
- Indefinido
```

Se estiver indefinido, registrar como pendente.

## 9. Definição da autonomia local do projeto

Durante a classificação, a IA deve solicitar o nível de autonomia local desejado para o projeto.

A autonomia local do projeto NÃO deve ser confundida com a autonomia de bootstrap da WB.

A autonomia local deve ser registrada posteriormente no contexto local do projeto.

Níveis possíveis:

```text
- baixa
- media
- alta
```

A IA deve também registrar:

```text
- justificativa da autonomia;
- limites da autonomia;
- decisões que exigem aprovação humana.
```

## 10. Documentação proporcional

A documentação deve acompanhar o tamanho do projeto.

```text
Projeto simples:
- README
- .workbench mínimo
- checklist curto
- CURRENT_STAGE claro

Projeto médio:
- requisitos básicos
- arquitetura resumida
- checklist por etapa
- critérios de aceite

Projeto complexo:
- requisitos formais
- arquitetura documentada
- decisões registradas
- workflows por módulo
- validações e rastreabilidade
```

## 11. Estrutura de pastas proporcional

Regra:

```text
Começar com a menor estrutura suficiente.
Escalar somente quando a complexidade justificar.
```

A IA não deve criar estrutura complexa em projeto simples.

## 12. Roteamento inicial

Após a classificação, a IA deve propor um caminho da biblioteca WB.

```text
Simples + Desktop:
workflows/simple-projects/desktop/

Simples + Console:
workflows/simple-projects/console/

Simples + Embarcado:
workflows/simple-projects/embedded/

Médio + Web:
workflows/medium-projects/web/

Médio + API:
workflows/medium-projects/api/

Médio + Desktop:
workflows/medium-projects/desktop/

Complexo + Multi-tecnologia:
workflows/complex-projects/multi-technology/

Complexo + Web/API/Banco:
workflows/complex-projects/fullstack/

Complexo + Embarcado:
workflows/complex-projects/embedded/
```

Se o caminho ainda não existir, a IA deve informar que o workflow especializado ainda está em construção e propor sua criação incremental.

## 13. Saída obrigatória

Ao final, a IA deve apresentar:

```text
- complexidade classificada;
- tipo de aplicação;
- tecnologias envolvidas;
- plataformas envolvidas;
- agente implementador previsto;
- nível de documentação recomendado;
- estrutura de pastas recomendada;
- workflow recomendado;
- autonomia local desejada;
- limites da autonomia local;
- lacunas encontradas;
- decisão que precisa de confirmação humana.
```

## 14. Atualização supervisionada do projeto alvo

Após confirmação humana, a IA deve sugerir atualização de:

```text
.workbench/PROJECT_WORKFLOW.md
.workbench/CURRENT_STAGE.md
```

Esses arquivos são governança oficial, portanto a atualização deve ser explícita e supervisionada.

## 15. Próximo contexto

Após confirmação da classificação, a IA deve seguir para o workflow indicado.

Exemplo:

```text
Se projeto simples desktop:
ler workflows/simple-projects/desktop/ENTRYPOINT.md

Se projeto médio API:
ler workflows/medium-projects/api/ENTRYPOINT.md

Se projeto complexo fullstack:
ler workflows/complex-projects/fullstack/ENTRYPOINT.md
```

Se o workflow indicado não existir, a IA deve parar e propor a criação incremental desse workflow.
