# Caso de Uso CDU10: Notificar Psicólogos

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Operacional / Automático

## Ator Principal
WhatsApp API

## Interessados e Interesses
- **Psicólogo**: Deseja receber notificações sobre novos agendamentos, cancelamentos ou alterações de consultas.
- **Paciente**: Deseja garantir que seu agendamento, cancelamento ou reagendamento seja comunicado ao psicólogo em tempo real.

## Pré-condições
- O psicólogo deve estar cadastrado com um número de WhatsApp válido.
- Um evento relevante (novo agendamento, cancelamento ou reagendamento) deve ter ocorrido no sistema.

## Garantia de Sucesso (Pós-condições)
- O psicólogo recebe a notificação em tempo real.
- O sistema registra o envio e a entrega da notificação.

## Cenário de Sucesso Principal
1. O sistema detecta um evento de agendamento, cancelamento ou reagendamento.
2. O sistema envia uma mensagem à WhatsApp API com os dados relevantes.
3. A WhatsApp API entrega a mensagem ao psicólogo.
4. O sistema confirma a entrega e registra o status.

## Extensões (Fluxos Alternativos)
- **3a. Número inválido ou falha na entrega**:
  1. O sistema registra o erro e tenta uma nova entrega posteriormente.
- **3b. Psicólogo bloqueou mensagens**:
  1. O sistema registra o bloqueio e envia um aviso alternativo (ex.: e-mail ou notificação no dashboard).

## Requisitos Especiais
- As mensagens devem ser personalizadas com detalhes do paciente e horário da consulta.
- Integração via Webhooks para resposta automática, quando necessário.

## Frequência de Ocorrência
Alta.