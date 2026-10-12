# Jornada+ | Gestão de Ponto e Jornada de Trabalho

Projeto feito com Java, Spring Boot, PostgreSQL e Docker (stack prevista; a definição final está na Etapa 4 do roadmap).

**Status:** Fase de Planejamento e Engenharia de Requisitos

O Jornada+ é uma plataforma web que simplifica e automatiza o controle de frequência, horas trabalhadas, horas extras e atrasos em pequenas empresas, substituindo processos manuais e planilhas por uma gestão centralizada e transparente.

## O problema

Pequenas empresas sofrem com o registro manual do ponto (papel ou planilhas), o que causa:

- falhas na apuração de horas;
- retrabalho para a gestão;
- falta de transparência para os colaboradores.

O Jornada+ oferece um ambiente acessível onde funcionários registram suas marcações e acompanham o histórico, enquanto gestores administram jornadas, corrigem divergências e geram relatórios consolidados.

## Quem usa

- **Gestor / Gerente:** cadastra a equipe, configura jornadas de trabalho, trata marcações (ajustes manuais), consulta atrasos e horas extras e exporta relatórios.
- **Funcionário:** registra as marcações diárias (Entrada, Almoço e Saída), altera a própria senha e consulta o espelho de ponto individual.

## As principais regras

Resumo das regras de negócio mais importantes. A lista completa (RF01 a RF16, prioridades e regras) está na [Especificação de Requisitos de Software (SRS - IEEE 830-1998)](https://github.com/Mickaellysilva/Jornada-/blob/main/docs/requisitos.md).

- Cada funcionário registra apenas as próprias marcações (Entrada, Almoço e Saída).
- Somente o gestor pode ajustar uma marcação manualmente.
- Atrasos e horas extras são calculados a partir da jornada configurada para cada funcionário.
- O funcionário sempre consegue consultar o seu espelho de ponto.

## Uma decisão difícil

Definir o que entra no MVP. O SRS tem 16 requisitos funcionais, mas para entregar valor cedo a prioridade é o fluxo central: registrar o ponto, ver o espelho e permitir ao gestor corrigir divergências. Relatórios e demais recursos ficam para depois.

## Onde eu errei

- Comecei a pensar em telas antes de fechar as regras de negócio, e tive de voltar aos requisitos.
- Subestimei os casos de borda, como marcações esquecidas ou duplicadas.

## O que ainda falta

Roadmap de desenvolvimento:

- [x] Etapa 1: Elicitação e Documentação de Requisitos (SRS)
- [ ] Etapa 2: Prototipagem de Telas (Figma)
- [ ] Etapa 3: Modelagem do Banco de Dados (DER / MER)
- [ ] Etapa 4: Definição da Arquitetura e Tech Stack
- [ ] Etapa 5: Desenvolvimento do MVP

Também faltam os diagramas de Casos de Uso e o modelo de banco de dados (em breve).

## O que eu faria na v2

- Integração com leitores biométricos ou geolocalização para validar as marcações.
- Notificações de atrasos e inconsistências para o gestor.
- Suporte a escalas diferentes (turnos, banco de horas).
- Aplicativo mobile para o registro de ponto.

## Autora

Mickaelly da Silva Costa
