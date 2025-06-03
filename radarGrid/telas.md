## 📱 Telas do Aplicativo – Grid Radar

| Tela Nº | Nome da Tela                   | Funcionalidades Principais                                                                     | Casos de Uso Relacionados |
| ------- | ------------------------------ | ---------------------------------------------------------------------------------------------- | ------------------------- |
| 1       | **Painel Inicial / Dashboard** | Exibir resumo de status por região, últimos alertas e tendências rápidas                       | UC04, UC09                |
| 2       | **Mapa de Risco**              | Visualizar mapa de calor com níveis de risco em tempo real                                     | UC04                      |
| 3       | **Detalhes da Região**         | Ver dados de sensores, clima, histórico de alertas, tendência e status atual de uma localidade | UC01, UC02, UC03, UC09    |
| 4       | **Relatar Anomalia**           | Usuário reporta manualmente uma falha ou comportamento suspeito                                | UC06                      |
| 5       | **Alertas Ativos**             | Lista de alertas com opção de validação ou encerramento                                        | UC05, UC10                |
| 6       | **Relatórios / Histórico**     | Visualização ou geração de relatórios por período, região, tipo de risco                       | UC07                      |
| 7       | **Administração (restrita)**   | Alterar regras de prioridade, visualizar logs, configurar regiões ou níveis de alerta          | UC08, UC10                |
| 8       | **Notificações**               | Visualizar notificações recebidas por risco alto, ações do sistema ou alertas confirmados      | UC05, UC10                |

---

### 🧩 Observações

- O app deve funcionar **offline** nas Telas 4 e 5, com **sincronização posterior** (RNF07).
- Telas 6 e 7 serão acessíveis apenas por **usuários autorizados** com perfil de gestão.
- A tela 3 incluirá gráficos e dados técnicos para engenheiros ou gestores.

---
