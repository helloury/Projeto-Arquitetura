# Caso de Uso CDU1: Agendar Consulta

## Escopo
Sistema de Atendimento Psicológico

## Nível
Objetivo do Paciente

## Ator Principal
Paciente

## Interessados e Interesses
- **Paciente**: deseja agendar consultas de forma rápida, segura e prática, receber comprovante de pagamento e notificações automáticas.
- **Psicólogo**: deseja ampliar o número de atendimentos, ter controle financeiro automatizado e acesso fácil às informações dos pacientes.
- **Sistema Externo de Notificações (WhatsApp API)**: Responsável por enviar lembretes e confirmações automáticas.

## Pré-condições
- O paciente deve estar cadastrado na plataforma.
- Deve haver psicólogos e horários disponíveis cadastrados.

## Garantia de Sucesso (Pós-condições)
- A consulta foi marcada.
- A notificação foi recebida.
- A contabilidade foi atualizada.
- O relatório do paciente foi aberto para anotações.
- A autorização de pagamento foi registrada.

## Cenário de Sucesso Principal
1. O paciente acessa a opção “agendamento”.
2. O paciente escolhe uma data e horário para a consulta.
3. O sistema exibe os horários e dias mais próximos com disponibilidade.
4. O paciente seleciona o psicólogo.
5. O paciente escolhe a forma de pagamento.
6. O paciente realiza o pagamento, e o sistema processa a transação.
7. O sistema confirma o agendamento e registra as informações.
8. O sistema envia os dados para o sistema de notificações externas (WhatsApp API).
9. O sistema gera e exibe o recibo.
10. O paciente encerra a sessão.

## Extensões (Fluxo Alternativo)
- **2a. Caso não haja psicólogos disponíveis na data/horário escolhido**:
  1. O sistema informa a indisponibilidade e sugere novas opções de data e horário.
  2. O paciente seleciona uma nova opção, e o sistema retoma o fluxo principal a partir do passo 3.
- **5a. Paciente precisa registrar o cartão para pagamento**:
  1. O sistema disponibiliza um campo com verificação de autenticação do cartão para novo registro.
  2. O sistema permite adicionar outro cartão.
  3. O sistema permite parcelar em até 2 vezes.
  4. O paciente finaliza a operação.
- **6a. Caso o pagamento falhe**:
  1. O sistema informa o erro e solicita atualização dos dados ou outra forma de pagamento.
  2. O paciente corrige, e o sistema retoma o fluxo principal no passo 7.
- **9a. Caso algum campo obrigatório esteja vazio**:
  1. O sistema exibe uma mensagem de erro informando os campos que devem ser preenchidos antes de prosseguir.

## Requisitos Especiais
- Integração com sistema externo de pagamento (ex.: Stripe, PayPal, PagSeguro).
- Envio automático de notificações via WhatsApp API.
- Dados sensíveis devem ser criptografados (conformidade com LGPD).
- O sistema deve estar disponível 24/7.

## Lista de Variantes Tecnológicas e de Dados
- API de pagamento configurada via HTTPS.
- Banco de dados relacional (MySQL/PostgreSQL).
- Sistema de notificações baseado em Webhooks.
- Aplicativo desenvolvido em ambiente web responsivo.

## Frequência de Ocorrência
Alta (realizado diversas vezes por dia).
