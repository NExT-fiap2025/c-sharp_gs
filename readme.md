Claro! Abaixo está o **Documento Completo de Requisitos do Projeto PowerGuard**, incluindo:

1. Visão geral
2. Requisitos Funcionais (RF)
3. Requisitos Não Funcionais (RNF)
4. Regras de Negócio (RN)
5. Requisitos Técnicos (RT)
6. Casos de Uso (UC)
7. Telas do Aplicativo e Funcionalidades

---

# 📄 Documento de Requisitos – PowerGuard

---

## 🔰 1. Visão Geral do Projeto

O **PowerGuard** é uma solução inteligente voltada à mitigação de falhas energéticas causadas por eventos climáticos extremos. A proposta é oferecer um sistema distribuído, com sensores IoT, backend modular baseado em microserviços e um aplicativo mobile simples porém robusto. O sistema será capaz de detectar quedas de energia, identificar regiões críticas, acionar automaticamente autoridades e disponibilizar informações em tempo real à população.

* **Objetivo**: Automatizar a resposta a falhas de energia e proteger vidas e infraestruturas essenciais.
* **Como resolve**: Através de detecção em tempo real, priorização de áreas e integração com entidades de suporte.
* **Consequência esperada**: Diminuição de prejuízos, respostas mais rápidas e melhora na resiliência das comunidades afetadas.

---

## ✅ 2. Requisitos Funcionais (RF)

| Código | Descrição                                                         |
| ------ | ----------------------------------------------------------------- |
| RF01   | Detectar automaticamente falhas de energia por sensores           |
| RF02   | Classificar áreas por prioridade (ex: hospitais, escolas)         |
| RF03   | Acionar automaticamente órgãos públicos conforme o tipo de falha  |
| RF04   | Notificar usuários via aplicativo sobre falhas e estimativas      |
| RF05   | Registrar logs de falhas, ações e tempos de resolução             |
| RF06   | Exibir mapa com status de recuperação nas regiões                 |
| RF07   | Permitir que usuários registrem incidentes manualmente            |
| RF08   | Mostrar histórico de falhas por região e dados agregados          |
| RF09   | Permitir que administradores editem regras de resposta            |
| RF10   | Controlar remotamente religamento de energia via dispositivos IoT |
| RF11   | Exibir panorama geral de eventos registrados pelo usuário         |
| RF12   | Permitir cadastro e visualização de regiões afetadas              |
| RF13   | Registrar e exibir o tempo de interrupção em cada região          |
| RF14   | Coletar informações sobre prejuízos causados                      |
| RF15   | Exibir recomendações e boas práticas para situações de falha      |

---

## ⚙️ 3. Requisitos Não Funcionais (RNF)

| Código | Descrição                                                     |
| ------ | ------------------------------------------------------------- |
| RNF01  | Disponibilidade mínima de 99,5% do sistema                    |
| RNF02  | Tempo de resposta da API inferior a 2 segundos                |
| RNF03  | Suporte a 10.000 usuários simultâneos                         |
| RNF04  | App mobile deve funcionar offline com sincronização posterior |
| RNF05  | Backend com arquitetura modular e escalável                   |
| RNF06  | Criptografia de dados sensíveis em trânsito e repouso         |
| RNF07  | Autenticação centralizada com Azure Active Directory          |

---

## 📜 4. Regras de Negócio (RN)

| Código | Descrição                                                                        |
| ------ | -------------------------------------------------------------------------------- |
| RN01   | Incidentes em hospitais sempre têm prioridade máxima                             |
| RN02   | Locais com 3+ falhas em 24h são classificados como críticos                      |
| RN03   | Apenas administradores podem alterar regras do sistema                           |
| RN04   | Regiões sem sensores são sinalizadas como risco se houver falha não identificada |
| RN05   | Toda comunicação com autoridades deve ser registrada com timestamp               |

---

## 💻 5. Requisitos Técnicos (RT)

| Código | Descrição                                                     |
| ------ | ------------------------------------------------------------- |
| RT01   | Mobile em **React Native** com uso de **AsyncStorage**        |
| RT02   | API Gateway e serviços em **Java (Spring Boot)**              |
| RT03   | Microserviço especializado em **C# (.NET Core)**              |
| RT04   | Serviço de IoT usando **Python + Flask + MediaPipe**          |
| RT05   | Banco de dados **Oracle**                                     |
| RT06   | Hospedagem em **Microsoft Azure** com suporte a AD, DNS e VMs |
| RT07   | Comunicação RESTful entre serviços com autenticação JWT       |
| RT08   | Observabilidade via Azure Monitor e logs centralizados        |

---

## 🎯 6. Casos de Uso (UC)

### UC01 – Detecção Automática

* **Ator**: Sensor IoT
* **Descrição**: Identifica falhas e envia alerta para backend.

---

### UC02 – Visualizar Status

* **Ator**: Usuário
* **Descrição**: Consulta mapa e tempo estimado de recuperação.

---

### UC03 – Registro Manual

* **Ator**: Morador
* **Descrição**: Reporta queda de energia pelo app.

---

### UC04 – Ação de Recuperação

* **Ator**: Sistema
* **Descrição**: Envia comando para religamento remoto via IoT.

---

### UC05 – Administração de Regras

* **Ator**: Admin
* **Descrição**: Define prioridade, gatilhos e resposta automática.

---

### UC06 – Exibir Panorama Geral

* **Ator**: Usuário
* **Descrição**: Mostra histórico de falhas do próprio usuário.

---

### UC07 – Cadastro de Região Afetada

* **Ator**: Usuário
* **Descrição**: Salva local afetado via bairro, cidade ou CEP.

---

### UC08 – Registro de Tempo de Falha

* **Ator**: Usuário
* **Descrição**: Insere tempo real ou estimado da interrupção.

---

### UC09 – Informar Prejuízos

* **Ator**: Usuário
* **Descrição**: Relata danos e prejuízos em estabelecimentos ou casas.

---

### UC10 – Ver Recomendações

* **Ator**: Usuário
* **Descrição**: Consulta orientações e boas práticas preventivas.

---

## 📱 7. Telas do Aplicativo e Funcionalidades

| Tela   | Nome                 | Funcionalidades                        |
| ------ | -------------------- | -------------------------------------- |
| Tela 1 | Panorama Geral       | Resumo de eventos anteriores (UC06)    |
| Tela 2 | Localização Atingida | Cadastro e consulta de regiões (UC07)  |
| Tela 3 | Tempo de Interrupção | Registro de duração da falha (UC08)    |
| Tela 4 | Prejuízos Causados   | Inserção de prejuízos e danos (UC09)   |
| Tela 5 | Recomendações        | Exibição de orientações e dicas (UC10) |

---

Deseja que eu gere este conteúdo em `.docx` ou `.pdf` formatado para envio ou entrega? Posso também exportar como markdown para integração direta no Notion, GitHub ou outro repositório de projeto.
