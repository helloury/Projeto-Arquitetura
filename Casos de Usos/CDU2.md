# Caso de Uso CDU2: Reagendar Consulta

## Escopo

Sistema de Atendimento Psicológico Automatizado

## Nível

Objetivo do Paciente

## Ator Principal

Paciente

## Interessados e Interesses

- **Paciente**: Deseja alterar a data e o horário de uma consulta já marcada, de forma rápida e simples.
- **Psicólogo**: Deseja manter seu cronograma atualizado automaticamente, evitando conflitos de agenda.

## Pré-condições

- O paciente deve estar logado no sistema.
- O paciente deve possuir uma consulta previamente agendada e confirmada.

## Garantia de Sucesso (Pós-condições)

- A consulta foi reagendada com sucesso.
- O psicólogo e o paciente foram notificados da alteração.
- O sistema atualizou automaticamente o registro e os relatórios associados.

## Cenário de Sucesso Principal

- O paciente acessa a opção “Histórico”.
- O paciente seleciona a consulta que deseja reagendar.
- O paciente escolhe uma nova data e horário.
- O sistema exibe os psicólogos disponíveis para o novo horário.
- O paciente confirma o reagendamento.
- O sistema atualiza a agenda e envia notificações automáticas via WhatsApp API.

## Extensões (Fluxos Alternativos)

- **3a. Se não houver disponibilidade para a data/horário escolhido**:
  1. O sistema sugere horários próximos ou outro psicólogo.
  2. O paciente escolhe uma nova opção e retoma o fluxo principal a partir do passo 4.
- **5a. Se o paciente desistir de reagendar**:
  1. O sistema mantém a consulta original.

## Requisitos Especiais

- Comunicação via API de notificações (WhatsApp).
- Atualização automática dos registros de pagamento e relatórios.

## Frequência de Ocorrência

Média.