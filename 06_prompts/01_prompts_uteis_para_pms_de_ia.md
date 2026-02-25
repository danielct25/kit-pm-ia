# Prompts Úteis para Product Managers de IA

> Esta é uma coleção de prompts de Engenharia de Prompt para serem usados com Modelos de Linguagem Grandes (LLMs) como GPT-4, Claude 3, Llama 3 ou Gemini. Eles são projetados para acelerar tarefas comuns do dia a dia de um Gerente de Produto de IA. Lembre-se: a qualidade da saída depende da qualidade e do contexto que você fornece na entrada.

---

### 1. Brainstorming de Oportunidades de IA

**Objetivo:** Gerar ideias de como a IA pode resolver problemas de clientes ou melhorar um produto existente.

**Como usar:** Substitua o texto entre colchetes `[ ]` pelo seu contexto específico.

```
# Persona

Você é um Gerente de Produto de IA sênior, com vasta experiência em identificar oportunidades de alto impacto para aplicar machine learning e IA em produtos digitais. Seu objetivo é pensar de forma criativa, mas também prática, focando em problemas reais do usuário.

# Contexto

Estou trabalhando em um produto que é [descreva o produto, ex: uma plataforma de e-learning para profissionais de tecnologia].

Nossos principais usuários são [descreva o perfil do usuário, ex: desenvolvedores de software júnior a pleno].

O principal problema que eles enfrentam é [descreva o problema, ex: dificuldade em encontrar projetos práticos para aplicar o que aprendem nos cursos].

As métricas que mais importam para nós são [descreva as métricas, ex: engajamento (tempo na plataforma) e taxa de conclusão de cursos].

# Tarefa

Gere 5 ideias de features ou capacidades de IA que poderiam resolver o problema do nosso usuário e impactar positivamente nossas métricas. Para cada ideia, descreva:

1.  **Nome da Ideia:** Um nome curto e descritivo.
2.  **Problema do Usuário Abordado:** Como ela se conecta diretamente ao problema descrito.
3.  **Descrição da Solução (com IA):** Como a feature funcionaria do ponto de vista do usuário e qual a "mágica" da IA.
4.  **Tipo de IA Envolvida:** Qual a principal técnica de IA necessária (ex: Sistema de Recomendação, Geração de Linguagem Natural, Classificação).
5.  **Impacto Potencial:** Como essa ideia poderia impactar nossas métricas chave.
```

---

### 2. Geração de User Stories para uma Feature de IA

**Objetivo:** Traduzir uma ideia de feature de IA em user stories acionáveis para o time de desenvolvimento.

**Como usar:** Forneça uma descrição clara da feature que você tem em mente.

```
# Persona

Você é um Product Owner experiente, especialista em quebrar funcionalidades complexas em user stories claras e concisas, seguindo o formato "Como um [usuário], eu quero [ação], para que [benefício]".

# Contexto

Estamos planejando construir uma nova feature de IA chamada "Sumarizador de Reuniões".

A feature funciona da seguinte maneira: após uma videochamada em nossa plataforma, a IA processa a gravação e o transcrito para gerar um resumo dos principais pontos discutidos, itens de ação com os responsáveis e as principais decisões tomadas. O resumo será enviado por e-mail aos participantes e ficará disponível na página da reunião.

Os principais usuários são gerentes de projeto e líderes de equipe.

# Tarefa

Gere uma lista de user stories para a feature "Sumarizador de Reuniões". Inclua:

1.  **Happy Path:** Histórias que descrevem o fluxo principal e o sucesso da operação.
2.  **Casos de Borda (Edge Cases):** Histórias que consideram cenários menos comuns (ex: reunião sem áudio, transcrição de baixa qualidade, ninguém foi designado para uma ação).
3.  **Interação com a IA:** Histórias sobre como o usuário pode interagir com o resultado da IA (ex: editar um item de ação, corrigir um ponto do resumo).
```

---

### 3. Análise de Riscos Éticos e Vieses (Bias)

**Objetivo:** Pensar proativamente sobre os potenciais problemas éticos e de viés de uma aplicação de IA.

**Como usar:** Descreva a aplicação de IA e os dados que ela usará.

```
# Persona

Você é um especialista em Ética de IA e IA Responsável. Seu trabalho é analisar sistemas de IA para identificar potenciais fontes de viés, riscos de justiça, e consequências sociais não intencionais. Você é cético e pensa nos piores cenários para ajudar as equipes a construírem tecnologia mais segura.

# Contexto

Estamos desenvolvendo um modelo de IA para triagem de currículos. O objetivo é ajudar recrutadores a priorizarem os candidatos mais qualificados para uma vaga.

- **Input do Modelo:** O modelo receberá o texto do currículo do candidato (formação, experiência, habilidades) e a descrição da vaga.
- **Output do Modelo:** O modelo retornará uma pontuação de "adequação" de 0 a 100 para cada candidato.
- **Dados de Treinamento:** O modelo será treinado com currículos e decisões de contratação (quem foi contratado ou não) dos últimos 5 anos da nossa empresa.

# Tarefa

Realize uma análise de risco ético para este sistema. Identifique e descreva em detalhes:

1.  **Potenciais Vieses nos Dados:** Que tipos de vieses sociais ou históricos podem estar presentes nos nossos dados de treinamento? (Ex: viés de gênero, viés de universidade, viés de idade).
2.  **Riscos de Performance Injusta:** Como esses vieses podem levar o modelo a performar de maneira injusta para certos grupos de candidatos?
3.  **Riscos de Interpretação e Automação:** Quais são os riscos de um recrutador confiar cegamente na pontuação do modelo?
4.  **Consequências Não Intencionais:** Que outros impactos negativos a longo prazo este sistema poderia causar (ex: homogeneização da força de trabalho)?
5.  **Recomendações de Mitigação:** Para cada risco identificado, sugira pelo menos uma ação concreta que a equipe de produto e ciência de dados pode tomar para mitigar o risco.
```

---

### 4. Rascunho de um Documento de Requisitos do Produto (PRD)

**Objetivo:** Criar um primeiro rascunho de um PRD para uma feature de IA, que pode então ser refinado.

**Como usar:** Combine informações de outros documentos (Problem Statement, Opportunity Canvas) para dar o máximo de contexto.

```
# Persona

Você é um Gerente de Produto exemplar, conhecido por escrever PRDs claros, completos e bem estruturados. Você é ótimo em traduzir necessidades de negócio e de usuários em requisitos técnicos para a equipe de engenharia e ciência de dados.

# Contexto

- **Feature:** "Detecção de Anomalias em Faturas"
- **Problema:** Nossos clientes (departamentos financeiros) perdem dinheiro com faturas duplicadas ou fraudulentas que passam despercebidas.
- **Proposta de Valor:** Identificar e sinalizar automaticamente faturas suspeitas para revisão humana, economizando tempo e dinheiro.
- **Visão Geral da Solução:** Um modelo de IA analisará todas as novas faturas inseridas no sistema. Se uma fatura for considerada uma anomalia (ex: valor muito fora do padrão para um fornecedor, número de fatura duplicado com pequena alteração), ela será marcada com uma flag "Revisão Recomendada" e movida para uma fila especial.

# Tarefa

Gere um rascunho de um Product Requirements Document (PRD) para esta feature, usando a estrutura abaixo. Seja detalhado em cada seção.

- **1. Visão Geral e Objetivo**
- **2. Escopo e Requisitos do Produto (em formato de user stories)**
- **3. Requisitos Específicos da IA** (Tarefa do Modelo, Input, Output, Métricas de Sucesso Offline e Online, Latência)
- **4. Experiência do Usuário (UX) com IA** (Como o usuário vê a flag? O que acontece quando ele clica? Como ele dá feedback se a IA errou?)
- **5. Riscos e Mitigações** (Técnicos, de Produto, Éticos)
```
