Perfeito! Vamos agora definir a **Arquitetura de Microserviços do Grid Radar**, com base nas tecnologias obrigatórias por disciplina:

- **Java (Spring Boot)** → Microsserviços principais da disciplina de AOS
- **C# (.NET Core)** → Análise de risco e agregações inteligentes (disciplina de C#)
- **Python** → Coleta de dados IoT/sensores ambientais e integração com APIs externas (disciplina de IoT)

---

# 🧱 Arquitetura de Microserviços – Grid Radar

## 🌐 API Gateway (Java)

- **Função:** Centralizar chamadas do frontend e autenticação
- **Tecnologia:** Spring Cloud Gateway
- **Autenticação:** JWT

---

## 🔷 Microserviços Java (Spring Boot – AOS)

| Microserviço  | Função                                               | Rotas REST Exemplares                                 |
| ------------- | ---------------------------------------------------- | ----------------------------------------------------- |
| `ms-user`     | Cadastro e login de usuários                         | `POST /auth/register`, `POST /auth/login`, `GET /me`  |
| `ms-alert`    | Registro e status de alertas                         | `POST /alert`, `PUT /alert/{id}/status`, `GET /alert` |
| `ms-location` | Cadastro de regiões e visualização de status         | `POST /location`, `GET /location/status`              |
| `ms-report`   | Geração e exportação de relatórios                   | `GET /report/region`, `GET /report/period`            |
| `ms-admin`    | Regras de prioridade, logs e configurações restritas | `GET /admin/rules`, `PUT /admin/rules`, `GET /logs`   |

---

## 🟦 Microserviço C# – `ms-analytics`

- **Disciplina:** C# (Análise e processamento de dados)
- **Função:** Agrupar, cruzar e prever padrões de risco com base nos dados de sensores, clima e histórico.
- **Tecnologia:** .NET Core 8 + LINQ + EF + Web API
- **Rotas REST:**

  ```
  GET /analytics/summary
  GET /analytics/risk-trend?region=xxx
  GET /analytics/prediction?cep=xxx
  POST /analytics/process-data (interno)
  ```

> Este microserviço realiza **detecção preditiva**, analisando grandes volumes de dados e retornando alertas antes que o risco se concretize.

---

## 🟩 Microserviço Python – `ms-iot-ingestion`

- **Disciplina:** Physical Computing / IoT
- **Função:** Obter dados de sensores climáticos ou consumir APIs públicas de clima.
- **Tecnologia:** Python + FastAPI + Requests + integração com MediaPipe (se houver visual)
- **Responsabilidades:**

  - Coletar dados de umidade, temperatura, consumo etc.
  - Consultar APIs como OpenWeatherMap
  - Simular sensores com arquivos JSON ou fluxos periódicos

- **Rotas REST:**

  ```
  GET /iot/sensors/live
  POST /iot/sensors/mock
  GET /iot/weather/current
  ```

---

## 📦 Banco de Dados (Oracle – por serviço)

| Serviço           | Banco Isolado  |
| ----------------- | -------------- |
| ms-user           | `users_db`     |
| ms-alert          | `alerts_db`    |
| ms-location       | `locations_db` |
| ms-report         | `reports_db`   |
| ms-analytics (C#) | `analytics_db` |
| ms-iot-ingestion  | `iot_db`       |

---

## 📲 Mobile Frontend (React Native)

- Acesso a:

  - Mapa de risco
  - Notificações
  - Relatos manuais
  - Tendência de risco
  - Visualização dos dados do C# e Python via API Gateway

---

## 🔁 Integrações entre micros

| Serviço Origem     | Serviço Destino | Propósito                           |
| ------------------ | --------------- | ----------------------------------- |
| `ms-iot-ingestion` | `ms-analytics`  | Enviar dados de sensores            |
| `ms-analytics`     | `ms-alert`      | Gerar alerta automaticamente        |
| `ms-alert`         | `ms-report`     | Incluir alertas nos relatórios      |
| `ms-admin`         | Todos           | Definir regras, políticas e limites |

---
