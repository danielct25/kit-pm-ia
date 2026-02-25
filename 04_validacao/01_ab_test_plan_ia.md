> # Plano de Teste A/B para Features de IA

**Produto:** [Nome do Produto]
**Feature:** [Nome da Feature de IA]
**Autor:** [Seu Nome]
**Data:** [DD/MM/AAAA]
**Versão:** 1.0

> Este documento descreve o plano para executar um teste A/B para validar o impacto de uma nova feature ou modelo de IA. O objetivo é medir com rigor estatístico se a nova versão (com IA) é melhor do que a versão de controle (sem IA ou com um modelo antigo).

---

### 1. Visão Geral

*   **Contexto:** [Descreva brevemente o que está sendo testado. Ex: "Estamos testando um novo modelo de recomendação de produtos na página inicial contra o nosso modelo atual baseado em popularidade."]
*   **Período do Teste:** De [DD/MM/AAAA] a [DD/MM/AAAA] (ou até atingir o tamanho da amostra necessário).

### 2. Hipótese

*   **Hipótese:** "Se [exibirmos o novo modelo de recomendação de IA (Variante B)] para [usuários na página inicial], então [veremos um aumento na taxa de cliques (CTR) nos produtos recomendados] porque [as recomendações serão mais personalizadas e relevantes para os interesses do usuário]."

    *   **SE** [Ação/Mudança - O que vamos fazer?]
    *   **PARA** [Segmento de Usuários - Para quem?]
    *   **ENTÃO** [Resultado Esperado - O que esperamos que aconteça?]
    *   **PORQUE** [Justificativa - Por que acreditamos nisso?]

### 3. Métricas

| Tipo de Métrica | Métrica | Descrição e Como é Calculada |
| :--- | :--- | :--- |
| **Métrica Principal (North Star)** | [Ex: Taxa de Cliques (CTR) na lista de recomendação] | Esta é a métrica primária que determinará o sucesso do teste. Deve estar diretamente ligada à hipótese. *(Cálculo: Cliques / Impressões)* |
| **Métricas Secundárias** | [Ex: Taxa de Adição ao Carrinho] | Métricas que esperamos que também sejam influenciadas positivamente. Elas ajudam a contar a história completa. *(Cálculo: Adições ao carrinho a partir de um clique na recomendação / Cliques)* |
| | [Ex: Receita por Visitante (RPV)] | Ajuda a garantir que o aumento no CTR não está vindo de cliques de baixa qualidade. *(Cálculo: Receita total / Número de visitantes no grupo)* |
| **Métricas de Guardrail (Saúde)** | [Ex: Latência da Página] | Métricas para garantir que não estamos piorando a experiência em outras áreas. Se esta métrica piorar significativamente, o teste pode ser interrompido. *(Cálculo: Tempo de carregamento da página)* |
| | [Ex: Taxa de Rejeição (Bounce Rate)] | Garante que a nova feature não está confundindo ou frustrando os usuários. |
| | [Ex: Custo de Inferência por Usuário] | Específico para IA, monitora o custo computacional da nova versão. |

### 4. Configuração do Teste

*   **Grupos do Teste:**
    *   **Grupo A (Controle):** [Descreva a experiência do grupo de controle. Ex: "Vê a lista de produtos mais vendidos (regra de negócio atual)."]
    *   **Grupo B (Variante):** [Descreva a experiência do grupo variante. Ex: "Vê a lista de produtos recomendados pelo novo modelo de IA."]
    *   **(Opcional) Grupo C, D...:** [Se houver mais de uma variante.]

*   **Segmento de Audiência:**
    *   **Público-Alvo:** [Para quem o teste será direcionado? Ex: "Todos os usuários logados no Brasil que visitam a página inicial."]
    *   **Critérios de Exclusão:** [Quem será excluído? Ex: "Usuários internos da empresa."]

*   **Divisão de Tráfego:**
    *   Grupo A: 50%
    *   Grupo B: 50%

*   **Ferramenta de Teste A/B:** [Ex: Google Optimize, Optimizely, ferramenta interna]

### 5. Análise Estatística

*   **Tamanho da Amostra (Sample Size):** [Quantos usuários são necessários por grupo para alcançar significância estatística? Use uma calculadora de tamanho de amostra.]
    *   **Baseline (Taxa de Conversão Atual):** [Ex: 5%]
    *   **Efeito Mínimo Detectável (MDE):** [Ex: Aumento de 1% (de 5% para 5.05%)]
    *   **Significância Estatística (Alpha):** 95% (p-value < 0.05)
    *   **Poder Estatístico (Beta):** 80%

*   **Critério de Sucesso:**
    *   "Consideraremos o teste um sucesso se a Variante B mostrar um aumento estatisticamente significativo na métrica principal (CTR) com um nível de confiança de 95%, sem degradar as métricas de guardrail."

### 6. Riscos e Plano de Contingência

| Risco | Plano de Contingência |
| :--- | :--- |
| **Resultado Inconclusivo:** O teste termina sem um vencedor claro. | Analisar os resultados por sub-segmentos (ex: novos vs. recorrentes) para gerar novas hipóteses. Considerar rodar o teste por mais tempo se o tamanho da amostra não foi atingido. |
| **Métrica de Guardrail Piora:** A latência da página aumenta em mais de 10%. | Pausar o teste imediatamente. A equipe de engenharia investigará a causa da degradação da performance. |
| **Efeito "Novedade":** Os usuários clicam mais no início apenas porque é novo. | Analisar a performance ao longo do tempo. Se a elevação inicial desaparecer, pode ser necessário um teste mais longo para medir o comportamento estabilizado. |

### 7. Resultados e Decisão

*(Esta seção é preenchida após a conclusão do teste)*

*   **Resumo dos Resultados:**
    *   [Apresente uma tabela com os resultados de cada métrica para cada grupo, incluindo o uplift (melhora percentual) e o p-value.]

*   **Análise:**
    *   [Interprete os resultados. A hipótese foi validada? Houve algum resultado surpreendente?]

*   **Decisão Final:**
    *   (  ) **Lançar a Variante B:** A variante vencedora será lançada para 100% do tráfego.
    *   (  ) **Manter a Variante A:** O controle continua sendo a melhor experiência.
    *   (  ) **Iterar e Testar Novamente:** Os resultados foram inconclusivos ou geraram novas ideias que requerem um novo teste.

*   **Próximos Passos:**
    *   [Liste as ações a serem tomadas com base na decisão.]
