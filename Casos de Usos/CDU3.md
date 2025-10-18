# Caso de Uso CDU3: Cancelar Consulta

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
- O paciente deve estar logado no sistema.
- Deve haver uma consulta confirmada no histórico.

## Garantia de Sucesso (Pós-condições)
- A consulta foi removida da agenda.
- Notificações foram enviadas ao paciente e ao psicólogo.
- O sistema registrou o status “Cancelada” e atualizou os relatórios.

## Cenário de Sucesso Principal
1. O paciente acessa a opção “Histórico”.
2. O paciente seleciona a consulta desejada.
3. O paciente escolhe a opção “Cancelar”.
4. O sistema solicita confirmação do cancelamento.
5. O paciente confirma o cancelamento.
6. O sistema atualiza o status, envia notificações via WhatsApp API e gera um log interno.

## Extensões (Fluxos Alternativos)
- **3a. Paciente cancela fora do prazo permitido**:
  1. O sistema exibe um aviso e bloqueia a operação.
- **6a. Falha na comunicação com o servidor de notificações**:
  1. O sistema registra o log e tenta reenviar a notificação automaticamente.

## Requisitos Especiais
- Integração com WhatsApp API para envio de notificações.
- Registro automático de data e hora do cancelamento.

## Frequência de Ocorrência
Média.