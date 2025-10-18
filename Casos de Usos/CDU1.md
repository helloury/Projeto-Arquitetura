# Caso de Uso CDU1: Fazer Login

## Escopo
Sistema de Atendimento Psicológico Automatizado

## Nível
Usuário

## Ator Principal
Usuário (generalização de Paciente e Psicólogo)

## Interessados e Interesses
- **Paciente**: Deseja acessar o sistema para visualizar histórico, reagendar ou cancelar consultas, e efetuar pagamentos.
- **Psicólogo**: Deseja acessar o sistema para visualizar pacientes, agenda de consultas e relatórios.

## Pré-condições
- O usuário já deve possuir uma conta cadastrada.
- O sistema deve estar disponível e funcional.

## Garantia de Sucesso (Pós-condições)
- O usuário é autenticado.
- O sistema cria uma sessão de usuário segura.
- O sistema registra o horário de login (para auditoria/controle de sessão).
- O usuário é direcionado ao painel correspondente ao seu perfil (paciente ou psicólogo).

## Cenário de Sucesso Principal
1. O usuário acessa a tela de login do sistema.
2. O sistema exibe os campos "E-mail", "Senha" e as opções "Entrar" e "Esqueci minha senha".
3. O usuário preenche suas credenciais (e-mail e senha) e aciona a opção "Entrar".
4. O sistema valida as credenciais no serviço de autenticação.
5. O sistema autentica o usuário, cria a sessão e identifica seu perfil (Paciente ou Psicólogo).
6. O sistema redireciona o usuário para sua página inicial (dashboard) adequada.

## Extensões (Fluxos Alternativos)
- **3a. Campos de entrada vazios (Validação local)**:
  1. No passo 3 do fluxo principal, o usuário aciona "Entrar" sem preencher o e-mail ou a senha.
  2. O sistema exibe uma mensagem de validação junto ao campo obrigatório (ex.: "Este campo é obrigatório").
  3. O sistema permanece na tela de login, aguardando a correção.
- **4a. Credenciais inválidas (E-mail não encontrado ou Senha incorreta)**:
  1. No passo 4 do fluxo principal, o sistema determina que o e-mail não existe ou que a senha fornecida não corresponde ao e-mail.
  2. Por razões de segurança, o sistema exibe uma mensagem de erro genérica (ex.: "E-mail ou senha inválidos. Por favor, tente novamente.").
  3. O sistema incrementa um contador de tentativas de falha para a conta (se o e-mail existir).
  4. O sistema permite que o usuário insira as credenciais novamente.
- **4b. Múltiplas tentativas de login falhas**:
  1. No passo 4a, o sistema detecta que o contador de tentativas de falha (ex.: 3 ou 5 tentativas) para uma conta foi excedido.
  2. O sistema bloqueia temporariamente a conta (ex.: por 15 minutos) ou exige um passo adicional (ex.: CAPTCHA).
  3. O sistema exibe uma mensagem informativa (ex.: "Sua conta foi temporariamente bloqueada devido a múltiplas tentativas de login falhas. Tente novamente mais tarde.").

## Fluxos de Falha (Exceções)
- **4c. Sistema ou Serviço de Autenticação Indisponível**:
  1. No passo 4 do fluxo principal, o sistema não consegue se comunicar com o banco de dados ou o serviço de autenticação.
  2. O sistema exibe uma mensagem de erro (ex.: "Nosso sistema está indisponível no momento. Por favor, tente novamente mais tarde.").
  3. O caso de uso falha.

## Relacionamentos (Links para outros Casos de Uso)
- Se o usuário selecionar "Esqueci minha senha" (no passo 2):
  - O sistema inicia o caso de uso UC Recuperar Senha.
- Se o usuário não possui conta (implícito no fluxo 4a):
  - A tela de login deve fornecer uma opção (ex.: "Não tem uma conta? Cadastre-se") que inicia o UC Cadastrar Usuário (CDU0a).

## Requisitos Especiais
- As senhas devem ser armazenadas de forma criptografada (utilizando hash e salt, ex.: bcrypt).
- A comunicação entre cliente e servidor deve ser segura (HTTPS).
- O sistema deve oferecer a funcionalidade "Esqueci minha senha" (link para UC Recuperar Senha).
- Opcional: O login pode ser compatível com provedores de identidade externos (ex.: Login com Google/Facebook via OAuth 2.0).

## Lista de Variantes Tecnológicas e de Dados
- Pode ser realizado via interface web (browser) ou aplicativo móvel (nativo/híbrido).
- O sistema deve utilizar tokens de sessão (ex.: JWT) com tempo de expiração definido para gerenciar a sessão do usuário.
- Banco de dados relacional (ex.: MySQL/PostgreSQL) para armazenamento de credenciais.

## Frequência de Ocorrência
Alta (diariamente, sempre que o usuário precisar acessar o sistema).