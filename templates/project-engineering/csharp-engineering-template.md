# C# Engineering Template

Este template orienta a engenharia de projetos ou módulos C#.

## Escopo

Aplicar quando o projeto utilizar:

```text
- C#
- .NET Framework
- .NET moderno
- WinForms
- WPF
- serviços backend em C#
- bibliotecas C#
```

## Engenharia obrigatória

A IA deve documentar em `docs/architecture/`:

```text
- tipo de aplicação C#;
- versão alvo do .NET;
- padrão de camadas;
- namespaces principais;
- fronteiras entre UI, BLL, DAL, DTL, serviços e infraestrutura;
- contratos entre camadas;
- estratégia de build;
- estratégia de testes;
- dependências externas.
```

## Regras de arquitetura

A IA deve evitar:

```text
- acoplamento direto de UI com banco, driver, protocolo ou infraestrutura;
- lógica de negócio dentro de Forms, Controllers ou Views;
- DTOs com lógica de negócio pesada;
- acesso direto a persistência fora da camada definida;
- classes utilitárias genéricas sem responsabilidade clara.
```

## Validação

Antes de liberar codação, deve existir:

```text
- estrutura de namespaces definida;
- fluxo de dependências entre camadas definido;
- critérios de build definidos;
- critérios de teste definidos;
- lista de arquivos ou áreas afetadas pela unidade atômica.
```
