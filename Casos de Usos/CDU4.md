# Caso de Uso CDU4: Efetuar Pagamento

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Objetivo do Paciente

## Ator Principal
Paciente

## Interessados e Interesses
- **Paciente**: Deseja pagar sua consulta de forma segura.
- **Psicólogo**: Deseja garantir o recebimento e registrar o pagamento automaticamente.

## Pré-condições
- O paciente deve estar logado no sistema.
- Deve existir uma consulta pendente de pagamento.

## Garantia de Sucesso (Pós-condições)
- O pagamento foi aprovado e registrado.
- O recibo foi gerado e enviado ao paciente.
- O sistema atualizou os relatórios financeiros e do paciente.

## Cenário de Sucesso Principal
1. O paciente acessa a opção “Pagamentos Pendentes”.
2. O paciente escolhe a consulta a ser paga.
3. O paciente seleciona o método de pagamento (cartão, Pix, boleto).
4. O sistema processa a transação.
5. O pagamento é aprovado.
6. O sistema gera o recibo e envia a confirmação via WhatsApp API.

## Extensões (Fluxos Alternativos)
- **4a. Pagamento recusado**:
  1. O sistema exibe um erro e oferece a opção de selecionar outro método de pagamento.
- **4b. Erro de autenticação do cartão**:
  1. O sistema solicita nova verificação ou registro de um novo cartão.

## Requisitos Especiais
- Integração com gateway de pagamento via Webhooks.
- Geração automática de recibo e envio de notificação via WhatsApp API.

## Frequência de Ocorrência
Alta.