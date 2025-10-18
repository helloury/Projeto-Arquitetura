# Caso de Uso CDU0b: Cadastro de Psicólogo (por Administrador)

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Operacional

## Ator Principal
Administrador

## Interessados e Interesses
- **Administrador**: Garante que somente profissionais validados sejam cadastrados no sistema.
- **Psicólogo**: Deseja ter acesso ao sistema para gerenciar consultas e pacientes.

## Pré-condições
- O administrador deve estar autenticado no sistema.

## Garantia de Sucesso (Pós-condições)
- O psicólogo foi cadastrado com sucesso e está habilitado a acessar as funcionalidades do sistema.

## Cenário de Sucesso Principal
1. O administrador acessa a opção “Cadastrar Psicólogo”.
2. O administrador preenche os dados obrigatórios (nome, e-mail, CRP, especialidade, senha inicial).
3. O sistema valida os dados fornecidos.
4. A conta do psicólogo é criada, e ele recebe uma notificação com os dados de acesso.

## Extensões (Fluxos Alternativos)
- **3a. Dados inválidos ou incompletos**:
  1. O sistema solicita a correção dos campos inválidos ou incompletos.
  2. O administrador corrige os dados e retoma o fluxo principal a partir do passo 3.
- **3b. Psicólogo já cadastrado**:
  1. O sistema informa que o psicólogo já está cadastrado e impede a duplicidade.

## Requisitos Especiais
- Confirmação do cadastro via e-mail.
- Validação do registro profissional (CRP).
- Conformidade com LGPD para proteção de dados pessoais.

## Lista de Variantes Tecnológicas e de Dados
- Banco de dados de usuários (ex.: MySQL/PostgreSQL).
- Criptografia de senha (ex.: bcrypt ou algoritmos equivalentes).
- Validação de registro profissional (CRP) via integração com base de dados oficial, se disponível.

## Frequência de Ocorrência
Baixa (realizado apenas quando há novos psicólogos a serem cadastrados no sistema).