# Caso de Uso CDU11: Enviar Mensagem de Confirmação de Consulta

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Operacional / Automático

## Ator Principal
WhatsApp API

## Interessados e Interesses
- **Paciente**: Deseja receber confirmação imediata após o agendamento ou reagendamento de uma consulta.
- **Psicólogo**: Deseja garantir que cada consulta seja confirmada automaticamente para o paciente.

## Pré-condições
- O paciente deve estar cadastrado com um número de WhatsApp válido.
- Uma consulta deve ter sido agendada ou reagendada.

## Garantia de Sucesso (Pós-condições)
- O paciente recebe a mensagem de confirmação da consulta.
- O sistema registra a confirmação e o status de entrega da mensagem.

## Cenário de Sucesso Principal
1. O sistema envia os dados da consulta para a WhatsApp API.
2. A WhatsApp API entrega a mensagem de confirmação ao paciente.
3. O sistema registra a entrega e qualquer resposta do paciente (se houver).

## Extensões (Fluxos Alternativos)
- **2a. Falha na entrega**:
  1. O sistema registra a falha e tenta reenviar a mensagem.
- **2b. Paciente não responde à confirmação**:
  1. O sistema pode enviar um lembrete automático 24 horas antes da consulta.

## Requisitos Especiais
- As mensagens devem ser padronizadas e personalizadas (incluindo nome do paciente, data e hora da consulta).
- O status de entrega deve ser registrado em banco de dados para fins de auditoria.

## Frequência de Ocorrência
Alta.