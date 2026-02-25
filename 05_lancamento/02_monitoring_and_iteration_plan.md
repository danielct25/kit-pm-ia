# Plano de Monitoramento e Iteração Pós-Lançamento (IA)

**Produto:** [Nome do Produto]
**Feature:** [Nome da Feature de IA]
**Autor:** [Seu Nome]
**Data:** [DD/MM/AAAA]

> O trabalho não termina no lançamento. Para produtos de IA, o pós-lançamento é ainda mais crítico. Modelos de IA podem degradar com o tempo (drift), o comportamento do usuário pode mudar e novas oportunidades de melhoria surgem constantemente. Este documento estabelece um plano para monitorar, manter e iterar na feature de IA para garantir seu sucesso a longo prazo.

---

### 1. Dashboards de Monitoramento

É essencial ter dashboards centralizados para acompanhar a saúde da feature. Crie links para cada um.

| Dashboard | Dono(a) | Métricas Principais | Link |
| :--- | :--- | :--- | :--- |
| **Dashboard de Adoção e Engajamento** | [Product Manager] | - WAUs/MAUs da feature<br>- Taxa de Adoção<br>- Frequência de Uso<br>- Taxa de Aceitação da Sugestão | [Link para o Looker/Tableau] |
| **Dashboard de Performance do Modelo** | [Cientista de Dados] | - Acurácia/Precisão/Recall (em produção)<br>- Model Drift (desvio de performance)<br>- Latência de Inferência<br>- Custo por Predição | [Link para o Datadog/New Relic/ferramenta interna] |
| **Dashboard de Feedback do Usuário** | [Product Manager] | - Pontuação de CSAT/NPS da feature<br>- Análise de sentimento dos comentários<br>- Categorias de feedback (ex: "sugestão errada", "lento") | [Link para o Zendesk/planilha] |

### 2. Rituais de Acompanhamento

| Ritual | Frequência | Participantes | Objetivo |
| :--- | :--- | :--- | :--- |
| **Revisão Semanal de Métricas** | Semanal | PM, Cientista de Dados, Engenheiro Líder | Revisar os dashboards, identificar anomalias e discutir o feedback da semana. Tomar decisões de curto prazo. |
| **Revisão Mensal de Performance** | Mensal | Time estendido (incluindo Marketing, Sucesso do Cliente) | Apresentar um resumo da performance da feature, compartilhar aprendizados e discutir o impacto nos KPIs de negócio. |
| **Sessão de Planejamento de Iteração** | Trimestral | PM, Cientista de Dados, Engenheiro Líder, UX Designer | Com base nos dados acumulados, decidir quais serão as próximas grandes apostas de melhoria para a feature (ex: retreinar o modelo, redesenhar a UX, adicionar novos dados). |

### 3. Plano de Retreinamento do Modelo

*   **Gatilhos para Retreinamento:** O que nos fará decidir que é hora de retreinar o modelo?
    *   **Automático (baseado em tempo):** [Ex: O modelo será retreinado automaticamente a cada 2 semanas com os novos dados coletados.]
    *   **Manual (baseado em performance):** [Ex: Se a métrica de acurácia cair abaixo de 90% por 3 dias consecutivos.]
    *   **Manual (baseado em novas fontes de dados):** [Ex: Quando uma nova fonte de dados relevante estiver disponível.]

*   **Processo de Retreinamento:**
    1.  Coleta e limpeza dos novos dados (incluindo feedback dos usuários).
    2.  Retreinamento do modelo.
    3.  Avaliação offline do novo modelo em comparação com o modelo em produção.
    4.  Se o novo modelo for significativamente melhor, ele é promovido para produção (geralmente via teste A/B ou shadow deployment).

### 4. Coleta e Análise de Feedback

*   **Canais de Coleta:**
    *   **Feedback Ativo:** [Ex: Pesquisas de satisfação (CSAT) exibidas após o uso da feature.]
    *   **Feedback Passivo:** [Ex: Botão "Dar Feedback" próximo ao resultado da IA.]
    *   **Feedback Indireto:** [Ex: Análise de tickets de suporte, menções em redes sociais, conversas com a equipe de vendas.]

*   **Processo de Análise:**
    *   O feedback é centralizado em [ferramenta, ex: Productboard, Planilha Google].
    *   A cada semana, o PM categoriza e resume os principais temas de feedback.
    *   Os exemplos mais impactantes (positivos e negativos) são compartilhados com a equipe para criar empatia e direcionar a priorização.

### 5. Backlog de Iteração

Este é um backlog vivo de ideias para melhorar a feature, alimentado por dados e feedback. Priorize usando um framework (ex: RICE, ICE).

| Ideia de Melhoria | Fonte da Ideia | Hipótese | Prioridade (1-5) |
| :--- | :--- | :--- | :--- |
| **Adicionar a feature X aos dados de treinamento** | Análise de performance | Se adicionarmos a feature X, o modelo será mais preciso para o segmento de usuários Y. | 1 |
| **Redesenhar a forma como as sugestões são apresentadas** | Teste de usabilidade | Se as sugestões forem mais visuais, a taxa de aceitação aumentará. | 2 |
| **Permitir que o usuário desfaça uma ação da IA** | Feedback de suporte | Se o usuário puder desfazer uma ação, sua confiança no sistema aumentará. | 3 |
| **Explorar uma nova arquitetura de modelo (ex: de Regressão para Redes Neurais)** | Pesquisa do time de ML | Uma nova arquitetura pode melhorar a acurácia geral em 10%. | 4 |

### 6. Comunicação de Melhorias

*   **Como comunicaremos as melhorias aos usuários?**
    *   **Melhorias Menores (ex: modelo um pouco mais preciso):** Geralmente não requerem comunicação. O produto simplesmente fica melhor.
    *   **Melhorias Maiores (ex: nova capacidade, mudança na UX):** Anunciar via notas de lançamento (release notes), posts no blog, ou notificações no aplicativo.
    *   O objetivo é reforçar a percepção de que o produto está constantemente evoluindo e ficando mais inteligente.
