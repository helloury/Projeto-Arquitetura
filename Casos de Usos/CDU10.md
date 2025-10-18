# Caso de Uso CDU10: Notificar Pacientes

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Operacional / Automático

## Ator Principal
WhatsApp API

## Interessados e Interesses
- **Paciente**: Deseja receber notificações automáticas de lembretes e atualizações sobre consultas.
- **Psicólogo**: Deseja garantir que os pacientes recebam lembretes sem necessidade de intervenção manual.

## Pré-condições
- O paciente deve estar cadastrado com um número de WhatsApp válido.
- Deve haver uma consulta agendada no sistema.

## Garantia de Sucesso (Pós-condições)
- O paciente recebe a notificação automática via WhatsApp.
- O status de envio da notificação é registrado no sistema.

## Cenário de Sucesso Principal
1. O sistema envia uma solicitação à WhatsApp API com os dados da consulta.
2. A WhatsApp API entrega a mensagem ao paciente.
3. O sistema confirma a entrega e registra o status.

## Extensões (Fluxos Alternativos)
- **2a. Número inválido ou falha na entrega**:
  1. O sistema registra o erro e tenta uma nova entrega após um determinado período.
- **2b. Paciente bloqueou mensagens**:
  1. O sistema registra o bloqueio e notifica o psicólogo sobre o problema.

## Requisitos Especiais
- Comunicação via Webhooks ou API REST segura.
- As mensagens devem ser personalizadas, incluindo o nome do paciente e a data/hora da consulta.

## Frequência de Ocorrência
Alta (notificações enviadas automaticamente 24/7).