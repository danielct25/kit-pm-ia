# Plano de Teste "Mágico de Oz" (Wizard of Oz - WoZ)

**Produto:** [Nome do Produto]
**Feature Conceitual:** [Nome da Feature de IA a ser simulada]
**Autor:** [Seu Nome]
**Data:** [DD/MM/AAAA]

> O teste "Mágico de Oz" é uma técnica de prototipagem de baixa fidelidade usada para validar uma feature de IA antes de construir qualquer modelo complexo. Nele, um humano (o "mágico") simula as respostas do sistema de IA em tempo real, sem que o usuário saiba. O objetivo é responder a perguntas críticas: **Alguém realmente quer isso? Como eles esperam que funcione? Qual é o valor percebido?**

---

### 1. Visão Geral e Objetivos

*   **Conceito da Feature:** [Descreva a feature de IA que será simulada. Ex: "Um chatbot que responde a perguntas dos clientes sobre o status de seus pedidos usando linguagem natural."]
*   **Objetivos do Teste:**
    1.  Validar a demanda e o valor percebido da feature antes de investir em desenvolvimento de ML.
    2.  Entender os tipos de perguntas e o vocabulário que os usuários realmente usam.
    3.  Identificar os casos de uso mais comuns e os casos de borda.
    4.  Coletar dados de interações reais que podem ser usados para treinar o modelo futuro.

### 2. Hipótese

*   **Hipótese Principal:** "Se oferecermos um chatbot 'inteligente' para responder perguntas sobre pedidos, então os usuários o utilizarão como primeiro canal de suporte, reduzindo o tempo gasto para obter uma resposta e aumentando sua satisfação."
*   **Perguntas a serem Respondidas:**
    *   Os usuários tentarão interagir com o chatbot?
    *   As respostas fornecidas (pelo 'mágico') resolvem o problema do usuário?
    *   Quão complexas são as perguntas dos usuários?
    *   Qual é a reação do usuário à experiência?

### 3. Configuração do Teste

| Componente | Descrição |
| :--- | :--- |
| **Interface do Usuário (O Palco)** | O que o usuário verá? (Ex: Uma simples caixa de chat em uma página do site). A interface deve parecer funcional, mas não precisa ser bonita. |
| **O "Mágico" (O Humano por trás da Cortina)** | Quem irá simular a IA? (Ex: O Product Manager, um UX Researcher). O mágico precisa de treinamento e de um "playbook". |
| **Ferramentas do Mágico (Os Controles)** | Como o mágico receberá a pergunta do usuário e enviará a resposta? (Ex: Um canal no Slack, um Google Doc compartilhado, um painel de admin simples). O sistema deve ser rápido o suficiente para simular uma resposta automática. |
| **Playbook do Mágico** | Um guia para o mágico com respostas pré-definidas para perguntas comuns, para garantir consistência e velocidade. Também deve incluir diretrizes sobre como lidar com perguntas inesperadas. |
| **Participantes** | Quem serão os usuários do teste? (Ex: 5-8 clientes reais recrutados que fizeram um pedido recentemente). |
| **Ambiente do Teste** | Onde o teste será conduzido? (Ex: Remotamente, via Zoom, com o participante compartilhando a tela). |

### 4. Roteiro do Teste

1.  **Introdução (5 min):**
    *   Apresente-se e explique o objetivo da sessão (sem revelar o segredo!). Ex: "Estamos testando uma nova forma de obter ajuda em nosso site. Gostaríamos que você usasse esta nova feature e nos dissesse o que pensa."
2.  **Cenário da Tarefa (10-15 min):**
    *   Dê ao usuário uma tarefa para completar. Ex: "Imagine que você quer saber onde está o pedido que fez na semana passada. Por favor, use a nova caixa de chat no canto da tela para descobrir."
    *   Peça ao usuário para pensar em voz alta.
3.  **Observação:**
    *   O **Mágico** recebe a pergunta, encontra a resposta (usando as ferramentas de back-office reais) e a envia de volta através da interface do chat, seguindo o playbook.
    *   O **Moderador** observa a interação, as reações do usuário e faz anotações.
4.  **Debriefing e Entrevista Pós-Teste (10 min):**
    *   "Como foi a experiência para você?"
    *   "A resposta foi o que você esperava? Foi útil?"
    *   "Quão valioso seria ter essa funcionalidade disponível sempre?"
    *   "Houve algo confuso ou frustrante?"
    *   (Opcional) "Para sua informação, as respostas que você recebeu hoje foram geradas por um membro da nossa equipe para simular como um sistema de IA funcionaria. Isso muda sua percepção da feature?"

### 5. Métricas e Critérios de Sucesso

*   **Métricas Quantitativas (se aplicável, para múltiplos testes):**
    *   Taxa de sucesso da tarefa (o usuário conseguiu a informação?).
    *   Tempo para completar a tarefa.
    *   Número de turnos na conversa.
*   **Métricas Qualitativas (o foco principal):**
    *   Feedback subjetivo sobre a utilidade e facilidade de uso (escala de 1 a 5).
    *   Comentários espontâneos e reações emocionais.
    *   Tipos de perguntas feitas (classificar em categorias).
*   **Critério de Sucesso:** "Consideraremos o teste um sucesso se a maioria dos participantes (ex: >70%) conseguir completar a tarefa com sucesso e expressar um sentimento positivo sobre a utilidade da feature, indicando que ela resolve um problema real."

### 6. Análise e Próximos Passos

*(A ser preenchido após os testes)*

*   **Principais Aprendizados:**
    1.  [Ex: Os usuários fazem perguntas muito mais complexas do que o esperado, frequentemente combinando duas questões em uma.]
    2.  [Ex: A expectativa de velocidade de resposta é altíssima (< 5 segundos).]
    3.  [Ex: A feature foi percebida como extremamente valiosa, com 4 de 5 usuários dizendo que a usariam sempre.]
*   **Decisão:**
    *   (  ) **Go:** Os resultados validam a hipótese. Vamos prosseguir com a criação de um PRD e o desenvolvimento de um MVP do modelo de IA.
    *   (  ) **Pivot:** A hipótese foi invalidada, mas descobrimos um problema adjacente mais importante a ser resolvido. Vamos refinar a ideia.
    *   (  ) **No-Go:** A feature não demonstrou valor suficiente para justificar o investimento.

*   **Próximos Passos:**
    *   [Ex: Usar o log das conversas como o primeiro dataset para treinar um modelo de classificação de intenção.]
