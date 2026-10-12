# Especificação de Requisitos de Software (SRS) — Jornada+

**Projeto:** Jornada+
**Sistema:** Jornada+
**Disciplina:** Tecnologia e Educação
**Equipe:** Mickaelly da Silva Costa
**Data:** 02/10/2026
**Padrão:** IEEE 830-1998

---

## 1. Introdução

### 1.1 Objetivo do sistema

O presente documento tem por objetivo formalizar os requisitos de software do sistema denominado Jornada+. Este documento segue o padrão SRS (Software Requirements Specification), estabelecido pelo IEEE 830-1998, constituindo o artefato técnico central da Etapa 1 do processo de desenvolvimento de software.

O Jornada+ é concebido como uma plataforma web destinada a auxiliar pequenas empresas no registro e acompanhamento da jornada de trabalho de seus funcionários. O sistema visa centralizar os registros de ponto, permitindo o acompanhamento da jornada, de modo que os funcionários possam registrar seus horários e os gestores possam realizar o gerenciamento desses registros.

A plataforma também contempla funcionalidades destinadas ao gerenciamento dos funcionários, à definição da jornada de trabalho, à visualização dos registros e à consulta das horas trabalhadas, além da identificação de funcionários com horas extras contabilizadas e atrasos.

De maneira específica, o sistema tem como objetivos:

- Permitir o cadastro, o gerenciamento e a disponibilização das informações dos funcionários pelos gestores do sistema;
- Gerar relatórios mensais sobre os dados da empresa;
- Permitir que os funcionários registrem suas horas de trabalho;
- Possibilitar que os gestores busquem, filtrem e visualizem os funcionários registrados no sistema;
- Identificar os funcionários que possuem horas extras e atrasos registrados.

---

## 2. Descrição Geral

### 2.1 Problema que será resolvido

Em pequenas empresas, a presença dos funcionários é registrada de maneira manual ou por meio de planilhas para acompanhar a jornada de trabalho, o que dificulta a conferência dos registros, gera sobrecarga e pode resultar em perda de produtividade.

O Jornada+ propõe-se a mitigar esse conjunto de problemas por meio do fornecimento de uma solução tecnológica acessível e intuitiva, que permita aos usuários registrar seu expediente de trabalho, além de visualizar seu histórico de registros.

### 2.2 Público-alvo

O sistema é direcionado, primariamente, a dois perfis de usuários:

- **Funcionários:** pessoas que poderão registrar o início e o fim de sua jornada de trabalho diária, além de consultar seu histórico de registros na empresa.
- **Gestores:** pessoas que poderão cadastrar funcionários, definir a jornada de trabalho, visualizar registros, consultar as horas trabalhadas, identificar atrasos e horas excedentes, além de gerar relatórios mensais.

---

## 3. Requisitos Funcionais

| ID | Nome | Descrição | Prioridade |
|---|---|---|---|
| RF01 | Controle de Acesso | O sistema deve ter perfis de login para Funcionário e Gerente, permitindo que qualquer funcionário registrado possua acesso ao sistema. | Alta |
| RF02 | Gerenciamento de Instituições | O sistema deve permitir que o gestor cadastre os funcionários, exclua os funcionários, defina a jornada de trabalho, visualize registros, consulte horas trabalhadas, identifique atrasos e horas excedentes, além de gerar relatórios mensais. | Alta |
| RF03 | Redefinição de Senha | O sistema deve permitir que o funcionário altere a senha provisória fornecida e solicite redefinição futura via e-mail cadastrado. | Média |
| RF04 | Login dos Gerentes | O sistema deve permitir que o gerente acesse sua conta informando o login e senha fornecidos pelo administrador. | Alta |
| RF05 | Login dos Funcionários | O sistema deve permitir que o funcionário acesse sua conta informando o login e senha fornecidos pelo administrador. | Alta |
| RF06 | Busca e Visualização de Funcionários | O sistema deve permitir que o gestor busque por funcionários e visualize os mesmos com seu nome completo, total de horas trabalhadas, horas excedidas e atrasos. | Média |
| RF07 | Atrasos de Funcionários | O sistema deve calcular o atraso do funcionário a partir de 1 minuto do horário definido. | Alta |
| RF08 | Filtragem Interna por Funcionários com Horas Excedentes | O sistema deve permitir que o gestor, ao visualizar um funcionário, veja quantas horas extras ele fez mensalmente, bem como os dias de trabalho extra. | Média |
| RF09 | Filtragem Interna por Funcionários com Atrasos | O sistema deve permitir que o gestor, ao visualizar um funcionário, veja quanto tempo o funcionário atrasou, bem como os dias de atraso. | Média |
| RF10 | Canal de Contato com a Administração | O sistema deve disponibilizar um formulário público permitindo informar e-mail e motivo do contato para solicitar cadastro ou esclarecer dúvidas, encaminhando a solicitação para a área administrativa. | Média |
| RF11 | Localização do Funcionário | O sistema deve permitir ao gerente visualizar se o funcionário bateu o ponto do seu local de trabalho ou não. | Média |
| RF12 | Registro de Ponto | O sistema deve permitir que o funcionário registre suas marcações de ponto (Entrada, Saída para Almoço, Retorno do Almoço, Saída), armazenando a data e hora exatas da ação. | Alta |
| RF13 | Histórico de Ponto Individual | O sistema deve permitir que o funcionário visualize o espelho do seu próprio ponto do mês atual e de meses anteriores, contendo os horários registrados e o saldo de horas. | Alta |
| RF14 | Ajuste/Tratamento de Ponto | O sistema deve permitir que o gestor insira marcações manuais, justifique faltas ou edite horários caso o funcionário tenha esquecido de bater o ponto, mantendo um log visual de que aquele registro foi alterado manualmente. | Alta |
| RF15 | Geração de Relatório de Espelho de Ponto | O sistema deve permitir que o gestor gere e exporte (em formato PDF ou Excel) o relatório mensal de horas (espelho de ponto) de um ou mais funcionários. | Baixa |
| RF16 | Configuração de Jornada de Trabalho | O sistema deve permitir que o gestor crie e vincule diferentes jornadas de trabalho aos funcionários (ex.: 08:00 às 18:00 com 2h de almoço), definindo também os dias úteis da semana. | Média |

---

## 4. Requisitos Não Funcionais

### 4.1 Segurança

| ID | Descrição |
|---|---|
| RNF01 | O sistema deve armazenar senhas de usuários utilizando algoritmos de hash criptográfico com fator de custo adaptativo, como bcrypt ou Argon2, sendo vedado o armazenamento em texto simples. |
| RNF02 | Toda a comunicação entre cliente e servidor deve ser realizada sobre protocolo HTTPS, com certificado SSL/TLS válido, garantindo a confidencialidade e integridade dos dados em trânsito. |
| RNF03 | O sistema deve implementar mecanismo de controle de acesso baseado em papéis (RBAC — Role-Based Access Control), assegurando que cada perfil de usuário acesse exclusivamente as funcionalidades a ele destinadas. |
| RNF04 | O sistema deve implementar proteção contra ataques de injeção de código, incluindo SQL Injection, XSS e CSRF, adotando mecanismos de validação, sanitização e tratamento seguro das entradas fornecidas pelos usuários. |
| RNF05 | O sistema deve manter registros de log para operações sensíveis, como autenticações, alterações de dados cadastrais, alterações de senhas e ações administrativas, para fins de auditoria e rastreabilidade. |
| RNF06 | Os dados pessoais dos usuários devem ser tratados em conformidade com a Lei Geral de Proteção de Dados Pessoais (LGPD — Lei 13.709/2018), garantindo medidas adequadas de proteção, bem como os direitos aplicáveis aos titulares dos dados, incluindo mecanismos de consentimento, portabilidade e exclusão de dados. |
| RNF07 | O sistema deve limitar ou bloquear temporariamente novas tentativas de autenticação após um número definido de tentativas consecutivas malsucedidas, reduzindo o risco de ataques de força bruta. |
| RNF08 | O sistema deve encerrar automaticamente a sessão do usuário após um período de inatividade (por exemplo, 30 minutos). |
| RNF09 | O sistema deve registrar a data e a hora das marcações de ponto utilizando o relógio do servidor, sincronizado via NTP, e nunca o horário do dispositivo do usuário. |
| RNF10 | As marcações de ponto não podem ser apagadas nem sobrescritas. Todo ajuste manual feito pelo gestor (RF14) deve gerar um novo registro, preservando o original, o autor, a data e a justificativa. |
| RNF11 | A localização do funcionário (RF11) deve ser coletada apenas no momento da marcação de ponto, mediante consentimento explícito. |
| RNF12 | Os registros de ponto devem ser mantidos pelo período mínimo exigido pela legislação trabalhista aplicável. |

### 4.2 Desempenho

| ID | Descrição |
|---|---|
| RNF13 | O registro de uma marcação de ponto deve ser concluído em até 2 segundos em condições normais de uso. |
| RNF14 | A geração do relatório mensal (RF15) para até 50 funcionários deve ser concluída em no máximo 10 segundos. |
| RNF15 | O sistema deve suportar pelo menos 100 usuários simultâneos sem degradação perceptível, considerando o pico de acessos na entrada e na saída do expediente. |
| RNF16 | O sistema deve estar disponível em pelo menos 99% do tempo, medido mensalmente. |

### 4.3 Portabilidade

| ID | Descrição |
|---|---|
| RNF17 | A interface deve ser responsiva, funcionando em computadores, tablets e celulares. |
| RNF18 | O sistema deve ser compatível com as duas últimas versões estáveis dos navegadores Chrome, Firefox, Edge e Safari. |
| RNF19 | O sistema deve ser executável em contêineres Docker, de modo a funcionar de forma equivalente em diferentes sistemas operacionais e ambientes. |
| RNF20 | As configurações dependentes de ambiente (banco de dados, credenciais, URLs) devem ser definidas por variáveis de ambiente, sem alteração no código-fonte. |

### 4.4 Manutenção

| ID | Descrição |
|---|---|
| RNF21 | O sistema deve possuir testes automatizados cobrindo, no mínimo, as regras de cálculo de atrasos e horas extras (RF07 a RF09). |
| RNF22 | O sistema deve registrar logs de erro e de operação em formato estruturado, para facilitar o diagnóstico de
