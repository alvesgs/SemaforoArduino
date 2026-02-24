# Semáforo 2.0

## Descrição
Projeto Arduino que implementa um sistema de semáforo inteligente com controle de pedestres. O sistema alterna entre as luzes de trânsito e possui um botão para ativar o pedestre atravessar, com indicadores visuais.

## Componentes Utilizados

### Pinos de Saída (LED Semáforo)
- **Pino 8** - LED Vermelho
- **Pino 9** - LED Amarelo
- **Pino 10** - LED Verde

### Pinos de Saída (LED Pedestre)
- **Pino 6** - LED Verde (Pedestre permitido)
- **Pino 7** - LED Vermelho (Pedestre proibido)

### Pino de Entrada
- **Pino 3** - Botão (INPUT_PULLUP)

## Funcionamento

### Sequência Padrão
1. **Luz Verde** ⏱️ 4 segundos
   - Semáforo: Verde
   - Pedestre: Vermelho (não pode atravessar)

2. **Luz Amarela** ⏱️ 2 segundos
   - Semáforo: Amarelo
   - Pedestre: Vermelho (não pode atravessar)

3. **Luz Vermelha** ⏱️ 4 segundos (normal) ou até 2 segundos (com ativação)
   - Semáforo: Vermelho
   - Pedestre: Vermelho (aguardando botão)

### Modo Pedestre
Quando o botão é pressionado durante a fase vermelha:
- LED verde do pedestre pisca (alternando aceso/apagado)
- Permanece por 2 segundos
- Retorna ao estado normal

## Como Usar

1. **Montagem do circuito** conforme os pinos especificados
2. **Carregar o código** no Arduino
3. **Funcionamento automático** - O semáforo funciona continuamente
4. **Ativar pedestre** - Pressionar o botão durante a luz vermelha

## Requisitos
- Arduino (Uno, Nano ou compatível)
- 5 LEDs
- 5 Resistores (220Ω recomendado)
- 1 Botão push
- 1 Resistor de 10kΩ para pull-up (ou usar INPUT_PULLUP)
- Protoboard e jumpers

## Notas Técnicas
- Comunicação serial em 9600 baud para debug
- Usa INPUT_PULLUP para o botão
- Status booleano para rastrear ativação de pedestre
- Delays em milissegundos para timing preciso

## Versão
2.0
