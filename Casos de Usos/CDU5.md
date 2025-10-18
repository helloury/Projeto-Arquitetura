# Caso de Uso CDU5: Cancelar Consulta

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Objetivo do Paciente

## Ator Principal
Paciente

## Interessados e Interesses
- **Paciente**: Deseja cancelar uma consulta agendada.
- **Psicólogo**: Deseja ser notificado de cancelamentos com antecedência.

## Pré-condições
- Paciente acessou “Visualizar Histórico”.
- O paciente deve estar logado no sistema.
- Deve haver uma consulta confirmada no histórico.
- Cancelamento permitido até 24h antes da consulta.

## Garantia de Sucesso (Pós-condições)
- A consulta foi removida da agenda.
- Notificações foram enviadas ao paciente e ao psicólogo.
- O sistema registrou o status “Cancelada” e atualizou os relatórios.

## Cenário de Sucesso Principal
1. Paciente seleciona “Cancelar Consulta”.
2. O sistema solicita confirmação do cancelamento.
3. Paciente confirma.
4. Sistema atualiza status da consulta.
5. Notificações enviadas para paciente e psicólogo
6. Contabilidade registra cancelamento.

## Extensões (Fluxos Alternativos)
- **6a. Falha na comunicação com o servidor de notificações**:
  1. O sistema registra o log e tenta reenviar a notificação automaticamente.

## Requisitos Especiais
- Integração com WhatsApp API para envio de notificações.
- Registro automático de data e hora do cancelamento.

## Frequência de Ocorrência
Média.