# Arduino Engineering Template

Este template orienta a engenharia de projetos Arduino e embarcados.

## Escopo

Aplicar quando o projeto utilizar:

```text
- Arduino
- ESP32
- firmware embarcado
- comunicação serial
- SPI
- I2C
- CAN
- GPIO
- timers
- interrupções
```

## Engenharia obrigatória

A IA deve documentar em `docs/architecture/`:

```text
- placas utilizadas;
- microcontroladores utilizados;
- arquitetura de firmware;
- separação entre hardware e lógica;
- protocolos utilizados;
- timers e interrupções;
- fluxo de comunicação;
- limitações de memória;
- dependências elétricas;
- requisitos temporais.
```

## Regras de arquitetura

A IA deve evitar:

```text
- lógica concentrada no loop principal;
- delays bloqueantes sem justificativa;
- acoplamento direto entre protocolo e hardware;
- múltiplas responsabilidades em um único módulo;
- temporização implícita não documentada.
```

## Validação

Antes de liberar codação, deve existir:

```text
- mapa de responsabilidades do firmware;
- definição dos módulos;
- contratos de comunicação;
- requisitos temporais documentados;
- riscos de hardware conhecidos;
- definição de validação de sinais e protocolos.
```
