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
2. O paciente preenche os dados obrigatórios (nome, e-mail, senha, data de aniversário).
3. O sistema verifica se é maior de 18 anos.
4. O usuario é maior de 18.
5. O sistema valida as informações.
6. A conta é criada, e o paciente recebe uma confirmação.

## Extensões (Fluxos Alternativos)
- **3. O usuário é menor de 18 anos:**
  1. O sistema identifica que a idade calculada é inferior a 18 anos.
  2. O sistema exibe uma mensagem de alerta informando que o cadastro online não é permitido para menores de idade.
  3. O sistema instrui o usuário a comparecer presencialmente à clínica, acompanhado de um responsável legal, para realizar a abertura do prontuário/cadastro.
  4. O sistema exibe os dados de contato e endereço da clínica.
  5. O sistema limpa os dados sensíveis preenchidos e encerra o caso de uso (o cadastro online não é efetivado).
- **5a. Dados inválidos ou incompletos**:
  1. O sistema informa os campos que devem ser corrigidos.
  2. O paciente corrige os dados e retoma o fluxo principal a partir do passo 3.
- **5b. E-mail já cadastrado**:
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