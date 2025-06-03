## 🎯 **Casos de Uso – Grid Radar**

---

### ✅ UC01 – Monitorar Sensores em Tempo Real

- **Ator**: Sistema
- **Descrição**: Coleta constante de dados dos sensores elétricos e ambientais instalados em regiões monitoradas.
- **Fluxo Principal**:

  1. O sistema se conecta aos sensores.
  2. Os dados de tensão, umidade, temperatura e consumo são recebidos.
  3. Os dados são salvos em banco e enviados ao motor analítico.

---

### ✅ UC02 – Coletar Previsões Climáticas

- **Ator**: Sistema
- **Descrição**: Integração com APIs meteorológicas públicas ou privadas.
- **Fluxo Principal**:

  1. O sistema consome dados climáticos de APIs confiáveis.
  2. Armazena informações como tempestades, chuvas fortes, ventos, etc.
  3. Atualiza o banco de dados de alertas meteorológicos.

---

### ✅ UC03 – Detectar Risco de Colapso

- **Ator**: Sistema (ms-analytics)
- **Descrição**: Com base em dados climáticos + sensores + padrões históricos, detecta risco de falha elétrica.
- **Fluxo Principal**:

  1. Recebe dados ambientais e de sensores.
  2. Roda modelo preditivo (por exemplo, regressão ou árvore de decisão).
  3. Se risco > 70%, gera alerta e log.

---

### ✅ UC04 – Exibir Mapa de Calor

- **Ator**: Usuário (órgão público ou operador)
- **Descrição**: Interface que mostra o risco por região em cores.
- **Fluxo Principal**:

  1. Usuário abre o painel.
  2. App consome API `/riskmap`.
  3. Mapa é renderizado com níveis de risco em tempo real.

---

### ✅ UC05 – Notificar Órgãos Públicos

- **Ator**: Sistema
- **Descrição**: Quando risco for elevado, sistema notifica órgãos pré-cadastrados.
- **Fluxo Principal**:

  1. Risco > 70% detectado.
  2. Verifica responsáveis cadastrados para a região.
  3. Envia notificação por e-mail, API ou SMS com protocolo.

---

### ✅ UC06 – Registrar Anomalias Manualmente

- **Ator**: Usuário (morador, agente)
- **Descrição**: Usuário pode relatar comportamentos suspeitos ou falhas percebidas manualmente.
- **Fluxo Principal**:

  1. Usuário acessa app.
  2. Seleciona local e tipo de anomalia.
  3. Sistema registra alerta manual vinculado à região.

---

### ✅ UC07 – Gerar Relatórios

- **Ator**: Administrador / gestor público
- **Descrição**: Gera relatórios por período, tipo de risco ou região.
- **Fluxo Principal**:

  1. Admin acessa painel.
  2. Define filtros (data, local, tipo).
  3. Sistema retorna PDF, CSV ou visualização.

---

### ✅ UC08 – Atualizar Regras de Prioridade

- **Ator**: Administrador
- **Descrição**: Permite alterar pesos e regras que priorizam regiões (escolas, hospitais).
- **Fluxo Principal**:

  1. Admin acessa painel administrativo.
  2. Seleciona categoria e prioridade.
  3. Salva nova regra que será aplicada nas análises futuras.

---

### ✅ UC09 – Visualizar Tendência de Risco

- **Ator**: Gestor / Engenheiro
- **Descrição**: Ver gráfico com tendência histórica de risco em determinada região.
- **Fluxo Principal**:

  1. Usuário seleciona cidade ou bairro.
  2. Sistema gera gráfico de tendência com base nos dados anteriores.
  3. Usuário visualiza evolução temporal e frequência de alertas.

---

### ✅ UC10 – Validar ou Encerrar Alerta

- **Ator**: Agente Público ou Admin
- **Descrição**: Após receber notificação, pode confirmar ou encerrar o alerta.
- **Fluxo Principal**:

  1. Recebe alerta (via app ou painel).
  2. Clica em “Validar” ou “Encerrar”.
  3. Sistema registra a ação e muda o status do alerta.

---

Claro! Abaixo está o **quadro com as Telas do Aplicativo do Grid Radar**, cada uma mapeada com suas **funcionalidades específicas** baseadas nos casos de uso definidos anteriormente:

---
