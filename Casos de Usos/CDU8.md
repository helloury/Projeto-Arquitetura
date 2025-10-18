# Caso de Uso CDU8: Gerar Relatório de Pacientes

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Objetivo do Psicólogo

## Ator Principal
Psicólogo

## Interessados e Interesses
- **Psicólogo**: Deseja gerar e salvar relatórios detalhados sobre os atendimentos realizados para cada paciente.

## Pré-condições
- O psicólogo deve estar logado no sistema.
- Deve existir registro de atendimento para o paciente.

## Garantia de Sucesso (Pós-condições)
- O relatório foi gerado e salvo no histórico do paciente.

## Cenário de Sucesso Principal
1. O psicólogo acessa a opção “Relatórios”.
2. O psicólogo escolhe o paciente.
3. O psicólogo preenche as informações do atendimento.
4. O sistema salva e associa o relatório ao paciente.

## Extensões (Fluxos Alternativos)
- **4a. Falha ao salvar relatório**:
  1. O sistema exibe uma mensagem de erro e permite o reenvio das informações.

## Requisitos Especiais
- Nenhum requisito especial identificado.

## Frequência de Ocorrência
Média.