# 📄 Documento de Requisitos – Grid Radar

---

## 🔰 1. Visão Geral do Projeto

O **Grid Radar** é um sistema de **prevenção de colapsos elétricos** em áreas urbanas e regiões críticas. Diferentemente do PowerGuard, que atua após a interrupção, o Grid Radar utiliza dados ambientais, padrões históricos, alertas climáticos e sensores locais para **prever e evitar** falhas de energia antes que aconteçam.

- **Objetivo:** Monitorar, prever e alertar sobre riscos iminentes de falhas elétricas.
- **Como resolve:** Através da análise de dados ambientais, padrões de consumo e previsões meteorológicas cruzadas com sensores distribuídos.
- **Consequência esperada:** Redução drástica de quedas de energia em áreas críticas, melhor alocação de recursos e resposta proativa por parte de prefeituras e concessionárias.

---

## ✅ 2. Requisitos Funcionais (RF)

| Código | Requisito Funcional                                                           |
| ------ | ----------------------------------------------------------------------------- |
| RF01   | Monitorar sensores ambientais e elétricos em tempo real                       |
| RF02   | Coletar previsões climáticas e alertas de tempestade                          |
| RF03   | Cruzar dados para detectar riscos iminentes de colapso                        |
| RF04   | Exibir mapa de calor com níveis de risco por região                           |
| RF05   | Notificar órgãos públicos automaticamente em caso de alerta                   |
| RF06   | Exibir painel de análise com gráficos de tendência                            |
| RF07   | Permitir que usuários registrem alertas ou anomalias locais                   |
| RF08   | Gerar relatórios por período ou por tipo de risco                             |
| RF09   | Sistema de classificação automática por prioridade (escolas, hospitais, etc.) |
| RF10   | Logar todos os alertas e ações tomadas pelo sistema                           |

---

## ⚙️ 3. Requisitos Não Funcionais (RNF)

| Código | Requisito Não Funcional                                         |
| ------ | --------------------------------------------------------------- |
| RNF01  | Disponibilidade mínima de 99,9%                                 |
| RNF02  | Tempo de resposta máximo de 1 segundo para alertas críticos     |
| RNF03  | Suporte a múltiplas regiões simultâneas                         |
| RNF04  | Criptografia em todas as transmissões de dados                  |
| RNF05  | Armazenamento seguro e auditável de logs                        |
| RNF06  | Alta escalabilidade para ingestão de dados IoT e metereológicos |
| RNF07  | App mobile com modo offline de observação e anotação            |

---

## 📜 4. Regras de Negócio (RN)

| Código | Regra de Negócio                                                                              |
| ------ | --------------------------------------------------------------------------------------------- |
| RN01   | Regiões classificadas como críticas devem gerar alertas com 15 minutos de antecedência mínima |
| RN02   | Alertas só devem ser enviados se risco for superior a 70%                                     |
| RN03   | Apenas administradores podem confirmar o status de um alerta                                  |
| RN04   | O sistema deve ignorar sensores fora do intervalo aceitável de calibração                     |
| RN05   | Se três alertas em uma semana forem ignorados, região entra em “modo de atenção reforçada”    |

---

## 💻 5. Requisitos Técnicos (RT)

| Código | Requisito Técnico                                                                        |
| ------ | ---------------------------------------------------------------------------------------- |
| RT01   | Backend principal em **Java (Spring Boot)** com microsserviços                           |
| RT02   | Microserviço de análise preditiva em **C# (.NET Core)**                                  |
| RT03   | Microserviço de coleta IoT e dados ambientais em **Python (MediaPipe ou API climática)** |
| RT04   | App mobile em **React Native + AsyncStorage**                                            |
| RT05   | Banco de dados **Oracle**, separado por contexto (risco, clima, sensores)                |
| RT06   | API Gateway Java com autenticação JWT                                                    |
| RT07   | Observabilidade e alertas via Azure Monitor                                              |

---

Perfeito! Abaixo estão os **Casos de Uso (UC)** para o projeto **Grid Radar**, organizados com base nos requisitos funcionais previamente definidos e cobrindo todas as interações relevantes do sistema, tanto para usuários finais quanto para agentes públicos e automações do sistema.

---
