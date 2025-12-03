# LISTA DE REQUISITOS – GERAL
A lista a seguir unifica todos os requisitos funcionais (RF) e não funcionais (RNF) identificados a partir de todas as fontes fornecidas.

## Requisitos Funcionais (RF)
**Módulo de Agendamento e Agenda:**
- RF01: O sistema deve oferecer uma agenda online para cada profissional, permitindo o registro de consultas e outros compromissos pessoais para otimizar a organização do tempo.
- RF02: O sistema deve permitir que o agendamento de consultas seja feito tanto pelo profissional quanto pelo próprio paciente, com base na disponibilidade de horários.
- RF03: O sistema deve permitir o cancelamento de consultas por ambas as partes (profissional e paciente), com regras de antecedência configuráveis (ex: até 3 horas antes da sessão).
- RF04: No momento do agendamento, o sistema deve permitir a designação de uma sala de atendimento específica para a consulta.
- RF05: O sistema deve integrar e sincronizar a agenda do profissional com os horários disponíveis para agendamento, prevenindo sobreposições.

**Módulo de Notificações e Comunicação:**
- RF06: O sistema deve enviar notificações automáticas para confirmação de presença com antecedência (ex: 24 horas antes).
- RF07: O sistema deve enviar um lembrete diário para o profissional com a lista de todos os seus agendamentos do dia.
- RF08: O sistema deve permitir a integração com aplicativos de mensagem (ex: WhatsApp) para o envio de lembretes e confirmações.

**Módulo de Pacientes e Prontuários:**
- RF09: O sistema deve permitir o cadastro completo de pacientes, incluindo dados pessoais (nome, idade, data de nascimento, endereço) e, para menores, os dados dos responsáveis.
- RF10: O sistema deve possuir um módulo de prontuário eletrônico sigiloso para cada paciente, onde o profissional pode registrar a evolução das sessões.
- RF11: O sistema deve permitir o armazenamento seguro dos prontuários, com opção de integração a serviços de nuvem (ex: Google Drive) de forma organizada.

**Módulo Financeiro e Relatórios:**
- RF12: O sistema deve oferecer um recurso de pagamento online integrado, vinculado diretamente às consultas agendadas.
- RF13: O sistema deve ter a funcionalidade de emissão de nota fiscal para os pagamentos realizados.
- RF14: O sistema deve gerar relatórios financeiros mensais consolidados para fins contábeis.
- RF15: O sistema deve gerar relatórios clínicos individuais por paciente (histórico de sessões, evolução), acessíveis ao psicólogo.
- RF16: O sistema deve oferecer planilhas ou visualizações individuais para cada paciente, facilitando a organização e análise dos atendimentos.

**Módulo de Administração e Segurança:**
- RF17: O sistema deve ter um mecanismo de autenticação segura (login e senha).
- RF18: O sistema deve permitir a exportação de dados do paciente em formato comum (PDF), conforme exigido pela LGPD.

**Requisitos Não Funcionais (RNF)**
- RNF01: O sistema deve ser uma plataforma Web responsiva, compatível e funcional em múltiplos dispositivos (desktops, tablets e smartphones).
- RNF02: O sistema deve ser seguro e confiável, garantindo a proteção de dados sensíveis (cadastrais, prontuários, pagamentos) através de criptografia e controles de acesso.
- RNF03: O sistema deve estar em total conformidade com a Lei Geral de Proteção de Dados (LGPD).
- RNF04: O acesso aos prontuários eletrônicos deve ser restrito apenas ao profissional responsável pelo atendimento.
- RNF05: O sistema deve ter uma interface intuitiva, clara e de fácil utilização.
- RNF06: O sistema deve apresentar um bom custo-benefício.
- RNF07: O sistema deve garantir alta disponibilidade e realizar backups automáticos e periódicos.
