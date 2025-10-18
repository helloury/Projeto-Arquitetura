# Documento de Visão – Sistema Web de Psicologia

## 1. Introdução

### 1.1 Propósito
O presente documento tem como objetivo descrever a visão geral do sistema web voltado para clínicas e profissionais da área de psicologia.  
Este documento fornece uma compreensão compartilhada entre os stakeholders sobre as principais funcionalidades, restrições, público-alvo e objetivos do sistema.

### 1.2 Escopo
O sistema permitirá o **agendamento e gerenciamento de consultas psicológicas**, a **comunicação automatizada entre psicólogos e pacientes** (via WhatsApp), além de **controle financeiro e geração de relatórios clínicos e administrativos**.  
O sistema será acessado via navegador web, sendo **responsivo e compatível com diferentes dispositivos** (computadores, tablets e smartphones).

### 1.3 Definições, Acrônimos e Abreviações
- **LGPD** – Lei Geral de Proteção de Dados  
- **RF** – Requisito Funcional  
- **RNF** – Requisito Não Funcional  
- **Usuário** – Pessoa com acesso ao sistema (psicólogo, paciente ou administrador)

### 1.4 Referências
- Lei nº 13.709/2018 – Lei Geral de Proteção de Dados (LGPD)  
- IEEE Std 830-1998 – Recommended Practice for Software Requirements Specifications  

---

## 2. Descrição Geral

### 2.1 Perspectiva do Produto
O sistema será uma **plataforma web** de fácil acesso e navegação, que centraliza a gestão de pacientes, agendamentos e pagamentos em um único ambiente.  
A integração com **WhatsApp** possibilitará notificações automáticas e mensagens de confirmação, reduzindo ausências e melhorando a comunicação entre profissionais e pacientes.

### 2.2 Funções do Produto
As principais funções do sistema incluem:
- Agendar, reagendar e cancelar consultas  
- Efetuar pagamento online e gerar nota fiscal  
- Cadastrar e visualizar pacientes  
- Gerar relatórios clínicos e financeiros  
- Enviar notificações e confirmações de consulta via WhatsApp  
- Gerenciar prontuários eletrônicos com segurança  

### 2.3 Usuários e Envolvidos

| Tipo de Usuário | Descrição | Necessidades |
|-----------------|------------|---------------|
| **Psicólogo** | Profissional que realiza atendimentos e gerencia sua agenda | Organizar horários, acessar prontuários, visualizar relatórios e acompanhar finanças |
| **Paciente** | Pessoa atendida pelo profissional | Agendar, reagendar ou cancelar consultas e receber notificações |
| **Administrador do Sistema** | Responsável técnico pela plataforma | Monitorar funcionamento, segurança e backups do sistema |

### 2.4 Restrições
- O sistema deve atender à **LGPD**, garantindo a confidencialidade dos prontuários  
- Deve ser desenvolvido em ambiente **Web responsivo**  
- Deve realizar **armazenamento seguro** e **backups automáticos**  

### 2.5 Suposições e Dependências
- O sistema depende de **conectividade com a Internet** e de **integração com a API do WhatsApp** para envio de mensagens  
- O módulo de pagamentos depende da integração com **serviços externos** (ex: Mercado Pago, Stripe, ou PagSeguro)

---

## 3. Casos de Uso Principais

| Código | Caso de Uso | Atores Envolvidos | Descrição |
|--------|--------------|------------------|------------|
| UC01 | Agendar consulta | Paciente, Psicólogo | Permite selecionar data, horário e profissional disponível para uma nova consulta |
| UC02 | Reagendar consulta | Paciente, Psicólogo | Permite alterar o horário de uma consulta previamente marcada |
| UC03 | Cancelar consulta | Paciente, Psicólogo | Permite cancelar a consulta dentro das regras de antecedência |
| UC04 | Efetuar pagamento | Paciente | Permite realizar o pagamento da consulta online |
| UC05 | Visualizar pacientes | Psicólogo | Permite listar todos os pacientes cadastrados |
| UC06 | Gerar relatório de pacientes | Psicólogo | Gera relatórios clínicos com histórico e evolução |
| UC07 | Emitir relatório financeiro | Psicólogo | Gera relatórios de pagamentos e ganhos |
| UC08 | Notificar pacientes via WhatsApp | Sistema | Envia mensagens automáticas de lembrete e confirmação |
| UC09 | Enviar mensagem de confirmação via WhatsApp | Sistema | Envia confirmação imediata após o agendamento |
| UC10 | Notificar psicólogos via WhatsApp | Sistema | Envia lista diária de atendimentos ao psicólogo |

---

## 4. Requisitos

### 4.1 Requisitos Funcionais (RF)

#### Módulo de Agendamento e Agenda
- **RF01:** O sistema deve oferecer uma agenda online para cada profissional  
- **RF02:** O sistema deve permitir que o agendamento de consultas seja feito pelo profissional ou paciente  
- **RF03:** O sistema deve permitir o cancelamento de consultas por ambas as partes com antecedência configurável  
- **RF04:** O sistema deve permitir a designação de uma sala específica para a consulta  
- **RF05:** O sistema deve sincronizar a agenda do profissional, prevenindo sobreposições  

#### Módulo de Notificações e Comunicação
- **RF06:** O sistema deve enviar notificações automáticas para confirmação de presença  
- **RF07:** O sistema deve enviar lembrete diário ao profissional com seus agendamentos  
- **RF08:** O sistema deve integrar-se ao WhatsApp para envio de lembretes e confirmações  

#### Módulo de Pacientes e Prontuários
- **RF09:** O sistema deve permitir cadastro completo de pacientes  
- **RF10:** O sistema deve possuir um prontuário eletrônico sigiloso por paciente  
- **RF11:** O sistema deve armazenar prontuários de forma segura, com integração opcional a serviços de nuvem  

#### Módulo Financeiro e Relatórios
- **RF12:** O sistema deve oferecer pagamento online vinculado às consultas  
- **RF13:** O sistema deve emitir nota fiscal dos pagamentos realizados  
- **RF14:** O sistema deve gerar relatórios financeiros mensais  
- **RF15:** O sistema deve gerar relatórios clínicos individuais  
- **RF16:** O sistema deve oferecer visualizações individuais por paciente  

#### Módulo de Administração e Segurança
- **RF17:** O sistema deve possuir autenticação segura (login e senha)  
- **RF18:** O sistema deve permitir exportar dados do paciente em formato PDF conforme LGPD  

---

### 4.2 Requisitos Não Funcionais (RNF)
- **RNF01:** O sistema deve ser web responsivo e compatível com diversos dispositivos  
- **RNF02:** O sistema deve garantir segurança e criptografia dos dados  
- **RNF03:** O sistema deve estar em conformidade com a LGPD  
- **RNF04:** O acesso aos prontuários deve ser restrito ao profissional responsável  
- **RNF05:** A interface deve ser intuitiva e de fácil uso  
- **RNF06:** O sistema deve oferecer bom custo-benefício  
- **RNF07:** O sistema deve garantir alta disponibilidade e realizar backups automáticos  

---

## 5. Protótipo Conceitual (Visão Geral da Interface)

O sistema apresentará:
- **Painel do Psicólogo:** calendário de agendamentos, pacientes e relatórios  
- **Painel do Paciente:** agenda pessoal e histórico de consultas  
- **Painel Financeiro:** relatórios mensais, pagamentos e notas fiscais  
- **Painel de Notificações:** configurações de envio e mensagens automáticas  

---

## 6. Critérios de Aceitação
- O sistema deve permitir a execução completa de todos os casos de uso descritos  
- Todas as notificações devem ser enviadas corretamente via WhatsApp  
- O sistema deve manter 100% de conformidade com a LGPD  
- Os relatórios devem ser gerados em formato PDF e exportáveis  

---

## 7. Conclusão
O Sistema Web de Psicologia proporcionará **gestão centralizada, comunicação eficiente e segurança de dados** para profissionais e pacientes, otimizando o agendamento, atendimento e controle financeiro da clínica.
