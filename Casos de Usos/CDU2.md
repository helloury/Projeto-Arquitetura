# Caso de Uso CDU2: Agendar Consulta

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
- O status do pagamento foi registrado (Pago ou Pendente)
- O relatório do paciente foi aberto para anotações.


## Cenário de Sucesso Principal
1. O paciente acessa a opção “agendamento”.
2. O paciente escolhe uma data e horário para a consulta.
3. O sistema exibe os horários e dias mais próximos com disponibilidade.
4. O paciente seleciona o psicólogo.
5. O sistema solicita a modalidade de pagamento (Pagamento Online ou Pagamento no Local).
6. O paciente seleciona "Pagamento no Local".
7. O sistema registra a intenção de pagamento pendente.
8. O sistema confirma o agendamento e registra as informações.
9. O sistema envia os dados para o sistema de notificações externas (WhatsApp API).
10. O sistema gera e exibe o comprovante de agendamento (com status de pagamento pendente).
11. O paciente encerra a sessão.

## Extensões (Fluxo Alternativo)
- **2a. Caso não haja psicólogos disponíveis na data/horário escolhido**:
  1. O sistema informa a indisponibilidade e sugere novas opções de data e horário.
  2. O paciente seleciona uma nova opção, e o sistema retoma o fluxo principal a partir do passo 3.
- **6a. O paciente opta pelo "Pagamento Online"**:
  1. O sistema redireciona para a escolha da forma de pagamento (Cartão de Crédito/Débito, PIX).
  2. O paciente insere os dados ou seleciona um cartão salvo.
  3. O sistema processa a transação.
  4. Caso o pagamento seja aprovado, o sistema altera o status para "Pago".
  5. O sistema retoma o fluxo principal no passo 8 (Confirmar agendamento).
- **6b. Caso o pagamento Online falhe (no fluxo da extensão 6a):**:
  1. O sistema informa o erro.
  2. O sistema pergunta se o paciente deseja tentar outro cartão ou mudar para "Pagamento no Local" para não perder o agendamento.
  3. O paciente decide a ação e o fluxo segue conforme a escolha.
- **6c. Paciente precisa registrar o cartão para pagamento(dentro do fluxo 6a):**
  1. O sistema disponibiliza um campo com verificação de autenticação do cartão para novo registro.
  2. O sistema permite adicionar outro cartão.
  3. O sistema permite parcelar em até 2 vezes.
  4. O paciente finaliza a operação.
- **9a. Caso algum campo obrigatório esteja vazio**:
  1. O sistema exibe uma mensagem de erro informando os campos que devem ser preenchidos antes de prosseguir.

## Requisitos Especiais
- Integração com sistema externo de pagamento para modalidade de pagamento online.
- Envio automático de notificações via WhatsApp API.
- Dados sensíveis devem ser criptografados (conformidade com LGPD).
- O sistema deve estar disponível 24/7.

## Lista de Variantes Tecnológicas e de Dados
- API de pagamento configurada via HTTPS. 
- Sistema de notificações baseado em Webhooks.
- Aplicativo desenvolvido em ambiente web responsivo.

## Frequência de Ocorrência
Alta (realizado diversas vezes por dia).
