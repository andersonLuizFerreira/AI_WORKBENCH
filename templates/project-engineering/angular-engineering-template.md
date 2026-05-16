# Angular Engineering Template

Este template orienta a engenharia de projetos Angular.

## Escopo

Aplicar quando o projeto utilizar:

```text
- Angular
- TypeScript frontend
- SPA
- Angular Material
- aplicações web modulares
```

## Engenharia obrigatória

A IA deve documentar em `docs/architecture/`:

```text
- módulos Angular;
- estratégia de componentes;
- fluxo de estado;
- contratos com APIs;
- serviços;
- guards;
- roteamento;
- separação entre UI e lógica;
- estratégia de ambiente;
- build e deploy.
```

## Regras de arquitetura

A IA deve evitar:

```text
- lógica pesada em componentes;
- acesso HTTP espalhado;
- estado implícito;
- dependências circulares;
- componentes gigantes;
- mistura de regras de negócio com renderização.
```

## Validação

Antes de liberar codação, deve existir:

```text
- mapa de módulos;
- definição de responsabilidades;
- contratos de API;
- fluxo de navegação;
- critérios de build;
- critérios de teste.
```
