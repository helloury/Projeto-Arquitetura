# Caso de Uso CDU2: Visualizar Histórico (Revisado)

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Objetivo do Paciente

## Ator Principal
Paciente

## Interessados e Interesses
- **Paciente**: Deseja acompanhar consultas passadas, status de consultas futuras, histórico de pagamentos e ter acesso rápido a opções de reagendamento ou cancelamento.
- **Psicólogo** (Indireto): Interessa-se pela consistência dos dados do histórico para suas próprias análises clínicas (provavelmente em outro Caso de Uso).

## Pré-condições
- O paciente está autenticado (logado) no sistema.

## Garantia de Sucesso (Pós-condições)
- O paciente visualiza seu histórico completo de consultas (passadas e futuras) e pagamentos.
- O paciente identifica claramente quais consultas futuras são elegíveis para reagendamento ou cancelamento.
- O paciente consegue iniciar os fluxos de reagendamento ou cancelamento a partir do histórico, quando permitido.


## Cenário de Sucesso Principal
1. O paciente acessa a seção “Meu Histórico” no sistema.
2. O sistema recupera e exibe uma lista de todas as consultas (passadas e futuras) e transações de pagamento, ordenadas por data (da mais recente para a mais antiga).
3. O paciente localiza e seleciona uma consulta futura (status “Agendada”).
4. O sistema verifica as regras de negócio (ex.: antecedência mínima para alteração).
5. Como a consulta é elegível para alteração, o sistema exibe os detalhes da consulta e as opções: “Reagendar Consulta” e “Cancelar Consulta”.
6. O paciente seleciona uma das opções (ex.: “Reagendar”).
7. O sistema inicia o caso de uso correspondente (ver seção “Relacionamentos”).


## Extensões (Fluxos Alternativos)
- **2a. Histórico vazio**:
  1. No passo 2 do fluxo principal, o sistema não encontra registros de consultas ou pagamentos para o paciente.
  2. O sistema exibe uma mensagem informativa (ex.: “Você ainda não possui histórico de consultas ou pagamentos.”).
  3. O caso de uso termina.

- **3a. Paciente seleciona consulta passada**:
  1. No passo 3 do fluxo principal, o paciente seleciona uma consulta com status “Realizada”, “Cancelada” ou “Não Compareceu”.
  2. O sistema exibe os detalhes da consulta e/ou pagamento associado.
  3. O sistema não apresenta as opções “Reagendar” ou “Cancelar”, pois não se aplicam a consultas passadas.

- **3b. Paciente seleciona um registro de pagamento**:
  1. No passo 3 do fluxo principal, o paciente seleciona um item que é um registro de pagamento (e não uma consulta).
  2. O sistema exibe os detalhes da transação (data, valor, status, método de pagamento, consulta associada se houver).
  3. O sistema não apresenta as opções “Reagendar” ou “Cancelar”.


- **5a. Consulta futura não elegível para alteração**:
  1. No passo 4 do fluxo principal, o sistema verifica que a consulta futura selecionada não atende às regras de negócio para alteração, sendo menos de 24hrs
  2. O sistema exibe os detalhes da consulta, mas oculta as opções “Reagendar” e “Cancelar”.
  3. O sistema exibe uma mensagem explicando por que a alteração não é permitida (“Alterações ou cancelamentos só são permitidos com mais de 24h de antecedência.”).

## Requisitos Especiais
- O histórico deve ser exibido em tempo real, refletindo o estado mais atual de agendamentos e pagamentos.
- As regras de negócio para elegibilidade de reagendamento/cancelamento devem ser claramente definidas e aplicadas.
- Conformidade com LGPD/HIPAA para armazenamento seguro de dados do paciente.

## Lista de Variantes Tecnológicas e de Dados
- Armazenamento seguro de dados do paciente (conformidade com LGPD/HIPAA).
- Integração com gateway de pagamento para exibir o status correto das transações.
- Banco de dados relacional para armazenamento de histórico.

## Frequência de Ocorrência
Média a alta.