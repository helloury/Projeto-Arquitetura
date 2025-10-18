# Caso de Uso CDU0a: Criar Conta Paciente

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Operacional

## Ator Principal
Paciente

## Interessados e Interesses
- **Paciente**: Deseja criar uma conta para acessar o sistema e utilizar seus serviços.
- **Psicólogo e Contabilidade**: Precisam garantir que os usuários registrados são válidos para manter a integridade do sistema.

## Pré-condições
- O paciente não possui uma conta no sistema.

## Garantia de Sucesso (Pós-condições)
- A conta foi criada com sucesso, e o paciente pode realizar login.

## Cenário de Sucesso Principal
1. O paciente acessa a opção “Criar Conta”.
2. O paciente preenche os dados obrigatórios (nome, e-mail, senha, informações pessoais).
3. O sistema valida os dados fornecidos.
4. A conta é criada, e o paciente recebe uma confirmação.

## Extensões (Fluxos Alternativos)
- **3a. Dados inválidos ou incompletos**:
  1. O sistema informa os campos que devem ser corrigidos.
  2. O paciente corrige os dados e retoma o fluxo principal a partir do passo 3.
- **3b. E-mail já cadastrado**:
  1. O sistema solicita o uso de outro e-mail.
  2. O paciente fornece um novo e-mail e retoma o fluxo principal a partir do passo 3.

## Requisitos Especiais
- Validação de e-mail e uso de senha segura (com criptografia).
- Conformidade com LGPD para proteção de dados pessoais.

## Lista de Variantes Tecnológicas e de Dados
- Banco de dados de usuários (ex.: MySQL/PostgreSQL).
- Criptografia de senha (ex.: bcrypt ou algoritmos equivalentes).

## Frequência de Ocorrência
Média (realizado apenas no primeiro acesso do paciente).