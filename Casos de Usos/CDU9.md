# Caso de Uso CDU9: Emitir Relatório Financeiro

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Objetivo do Contabilidade

## Ator Principal
Contabilidade

## Interessados e Interesses
- **Psicólogo**: Deseja consultar um relatório financeiro detalhado com informações sobre consultas, pagamentos e cancelamentos para um período específico.
- **Contabilidade**: gerar relatórios detalhados de receitas, pagamentos e cancelamentos


## Pré-condições
- O psicólogo deve estar logado no sistema.
- Sistema possui registros de pagamentos e consultas.

## Garantia de Sucesso (Pós-condições)
- O relatório financeiro foi gerado com dados de consultas, pagamentos e cancelamentos.

## Cenário de Sucesso Principal
1. O psicólogo acessa a opção “Relatorio Financeiro”.
2. Sistema exibe filtros de período e psicólogo.
3. Contabilidade aplica filtros.
4. Sistema gera relatório detalhado e permite exportar.

## Extensões (Fluxos Alternativos)
- **3a. Nenhum dado encontrado**:
  1. O sistema exibe uma mensagem informativa indicando que não há dados para o período selecionado.

## Requisitos Especiais
-Relatórios precisos e auditáveis, integração automática com pagamentos.

## Lista de variantes Tecnológicas e de Dados:
- Base de dados financeira, exportação PDF/Excel.

## Frequência de Ocorrência
Média a alta, conforme a necessidade.