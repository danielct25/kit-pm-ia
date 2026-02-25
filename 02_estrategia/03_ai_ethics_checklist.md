# Checklist de IA Responsável e Ética

**Produto:** [Nome do Produto]
**Feature:** [Nome da Feature de IA]
**Responsável:** [Seu Nome]
**Data da Avaliação:** [DD/MM/AAAA]

> Este checklist é uma ferramenta para Product Managers garantirem que estão construindo produtos de IA de forma responsável. Ele deve ser usado desde a concepção da ideia até o lançamento e monitoramento contínuo. O objetivo não é ter todas as respostas, mas sim provocar as discussões certas e documentar as decisões.

---

### Princípios Fundamentais de IA Responsável

Nós nos comprometemos com os seguintes princípios (adaptado de frameworks como o da Microsoft, Google, etc.):

1.  **Justiça (Fairness):** Nossos sistemas de IA devem tratar todas as pessoas de forma justa, sem perpetuar vieses históricos ou sociais.
2.  **Confiabilidade e Segurança (Reliability & Safety):** Nossos sistemas devem operar de forma confiável, segura e consistente, com mecanismos para lidar com falhas.
3.  **Privacidade e Segurança de Dados (Privacy & Security):** Respeitamos a privacidade dos dados dos usuários e protegemos seus dados contra acesso não autorizado.
4.  **Inclusão (Inclusiveness):** Nossos sistemas devem ser projetados para serem inclusivos e acessíveis a todas as pessoas, independentemente de suas habilidades ou características.
5.  **Transparência e Explicabilidade (Transparency & Explainability):** Devemos ser transparentes sobre como nossos sistemas de IA funcionam e capazes de explicar suas decisões.
6.  **Responsabilidade e Governança (Accountability):** Somos responsáveis pelo impacto de nossos sistemas e temos estruturas de governança para garantir a supervisão humana.

---

### Checklist de Avaliação

| Categoria | Questão | Resposta (Sim/Não/N/A) & Comentários |
| :--- | :--- | :--- |
| **1. Definição do Problema e Caso de Uso** | | |
| | O uso de IA é justificado e proporcional ao problema? Consideramos alternativas sem IA? | *Comentário: Descreva por que a IA é necessária e por que soluções mais simples não são suficientes.* |
| | O sistema tem um propósito benéfico claro? Avaliamos os potenciais usos indevidos ou consequências não intencionais? | *Comentário: Liste os benefícios e também os piores cenários de abuso da tecnologia.* |
| **2. Dados (O Combustível da IA)** | | |
| | Os dados de treinamento são representativos da população de usuários que queremos atender? | *Comentário: Detalhe a demografia dos dados e compare com a população-alvo. Aponte gaps.* |
| | Realizamos uma análise para identificar e mitigar vieses (bias) nos dados de treinamento (ex: gênero, raça, idade)? | *Comentário: Descreva as técnicas usadas (ex: análise de distribuição, ferramentas de fairness).* |
| | A coleta e o uso dos dados estão em conformidade com as regulações de privacidade (ex: GDPR, LGPD)? | *Comentário: Confirme com o time jurídico. Os usuários deram consentimento claro?* |
| | Os dados são de alta qualidade, precisos e relevantes para o problema? | *Comentário: Como a qualidade dos dados foi validada?* |
| **3. Modelo (A Lógica da IA)** | | |
| | O desempenho do modelo foi avaliado em diferentes subgrupos demográficos para garantir que não haja degradação da performance para grupos minoritários? | *Comentário: Apresente as métricas de acurácia/erro para cada segmento relevante.* |
| | Existe um plano para monitorar o desempenho do modelo em produção e detectar "model drift" (degradação de performance com o tempo)? | *Comentário: Descreva o processo de monitoramento e retreinamento.* |
| | Para decisões de alto impacto, o modelo oferece algum grau de explicabilidade (XAI)? Podemos explicar por que uma decisão específica foi tomada? | *Comentário: Qual técnica de XAI está sendo usada (ex: SHAP, LIME)? É compreensível para o usuário final?* |
| **4. Experiência do Usuário (A Interação com a IA)** | | |
| | O usuário entende que está interagindo com um sistema de IA? | *Comentário: Como isso é comunicado na interface?* |
| | O sistema tem um mecanismo para o usuário fornecer feedback sobre os resultados da IA (ex: "Esta recomendação foi útil?")? | *Comentário: Descreva o feedback loop.* |
| | Qual é o plano de fallback quando a IA falha, erra ou tem baixa confiança? O usuário tem uma saída ou uma alternativa? | *Comentário: Ex: "Não tem certeza? Fale com um especialista." ou oferecer uma ação manual.* |
| | A interface do usuário ajuda a gerenciar as expectativas, indicando o nível de incerteza ou confiança da IA? | *Comentário: Ex: "Aqui estão alguns resultados prováveis" em vez de "A resposta é X".* |
| **5. Governança e Responsabilidade** | | |
| | Quem é o responsável final pelo resultado do sistema de IA? | *Comentário: Defina o "dono" da feature ou do sistema.* |
| | Existe um processo claro para escalar e remediar problemas éticos ou de desempenho que surjam após o lançamento? | *Comentário: Descreva o canal de escalonamento (ex: comitê de ética, time de produto).* |
| | A equipe que desenvolveu o sistema é diversa e inclui diferentes perspectivas? | *Comentário: A diversidade da equipe ajuda a identificar uma gama mais ampla de problemas potenciais.* |

---

### Resumo da Avaliação e Próximos Passos

*   **Principais Riscos Identificados:**
    1.  [Ex: Risco de viés de gênero nos dados de treinamento devido à fonte de dados histórica.]
    2.  [Ex: Falta de um mecanismo de fallback claro para o usuário quando o modelo tem baixa confiança.]

*   **Plano de Ação para Mitigação:**
    1.  **Risco 1:** [Ex: Coletar novos dados para balancear o dataset e aplicar a técnica de re-sampling. Reavaliar a performance em 2 semanas.]
    2.  **Risco 2:** [Ex: O time de UX irá projetar um componente de interface para permitir que o usuário corrija a sugestão da IA. Priorizado para o próximo sprint.]

*   **Decisão:** (  ) Go - Aprovado para a próxima fase. (  ) No-Go - Requer mais trabalho nos pontos acima antes de prosseguir.
