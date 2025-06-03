# 📄 Documento de Arquitetura Orientada a Serviços (AOS) – Atualizado

**Projeto:** PowerGuard
**Plataforma:** Microsserviços RESTful com API Gateway em Java
**Banco de Dados:** Oracle (por serviço)
**Infraestrutura:** Microsoft Azure

---

## ✅ 1. Objetivo

Aplicar uma arquitetura de microsserviços moderna e desacoplada para o sistema PowerGuard, com responsabilidades bem definidas por contexto de domínio, cumprindo requisitos das disciplinas de AOS (Java), C# (análises) e IoT (Python).

---

## 🧱 2. Microserviços do Sistema

| Nome                | Linguagem  | Responsabilidade                                     |
| ------------------- | ---------- | ---------------------------------------------------- |
| `ms-user`           | Java       | Autenticação e perfil                                |
| `ms-event`          | Java       | Registro de eventos de falta de energia              |
| `ms-location`       | Java       | Cadastro e status de regiões afetadas                |
| `ms-impact`         | Java       | Registro de prejuízos causados                       |
| `ms-recommendation` | Java       | Boas práticas e orientações                          |
| `ms-admin`          | Java       | Painel de controle e regras                          |
| `**ms-analytics**`  | **C#**     | 📊 Análise de dados, históricos, médias e relatórios |
| `**iot-vision**`    | **Python** | 🎥 Reconhecimento de gestos com MediaPipe            |

---

## 🧩 3. Detalhamento por Microserviço

### 📘 `ms-user` (Java)

**Rotas REST**

```
POST /auth/register
POST /auth/login
GET  /auth/me
```

---

### 📗 `ms-event` (Java)

**Rotas REST**

```
POST /event/report
GET  /event/user/{id}
GET  /event/all
PUT  /event/{id}/status
```

---

### 📙 `ms-location` (Java)

**Rotas REST**

```
POST /location
GET  /location/user/{id}
GET  /location/status
```

---

### 📕 `ms-impact` (Java)

**Rotas REST**

```
POST /impact
GET  /impact/event/{id}
```

---

### 📒 `ms-recommendation` (Java)

**Rotas REST**

```
GET /recommendations
```

---

### 🧾 `ms-admin` (Java)

**Rotas REST**

```
GET /admin/rules
PUT /admin/rules
GET /admin/logs
```

---

### 🟦 `ms-analytics` (C# ✅)

**Função:** Consolidação e análise de dados para visualização, tomada de decisão e relatórios.

**Rotas REST**

```
GET /analytics/history?cep=XXXXX
GET /analytics/avg-interruption?city=São Paulo
GET /analytics/summary
GET /analytics/losses?region=XXXXX
```

> Integra-se via REST com os serviços Java para coleta de dados.

---

### 🟩 `iot-vision` (Python + MediaPipe ✅)

**Função:** Reconhecimento de gestos em vídeo para acionar eventos em ambientes escuros.

**Descrição:**

- Detecção de gestos em tempo real com câmera
- Aciona um POST local para o `ms-event` ao reconhecer sinal crítico
- Gera logs locais (ex: `event.json`)
- Simula ambientes com pouca iluminação

**Entrega física:**

- Repositório GitHub com código, README, vídeo e nomes/RM

---

## 🔁 4. Integração e Fluxo

- Frontend (React Native) → API Gateway (Java) → Microsserviços
- `ms-analytics` consome `ms-event`, `ms-impact`, `ms-location` por REST
- `iot-vision` roda localmente e se comunica com `ms-event` via POST

---

## 📌 5. Conformidade por Disciplina

| Disciplina                   | Microserviço(s)   | Linguagem                     | Foco                               |
| ---------------------------- | ----------------- | ----------------------------- | ---------------------------------- |
| **AOS**                      | Todos os Java     | Java + REST + Banco + Gateway |                                    |
| **C#**                       | `ms-analytics` ✅ | C# (.NET)                     | Relatórios, históricos, agregações |
| **IoT / Physical Computing** | `iot-vision` ✅   | Python + MediaPipe            | Detecção visual + eventos          |

---
