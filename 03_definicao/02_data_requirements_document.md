# Data Requirements Document (DRD) para Projetos de IA

**Produto:** [Nome do Produto]
**Feature:** [Nome da Feature de IA]
**Autor:** [Seu Nome]
**Data:** [DD/MM/AAAA]
**Versão:** 1.0

> Este documento é um complemento ao PRD e serve para detalhar especificamente as necessidades de dados para um projeto de Machine Learning. Ele alinha Product Managers, Cientistas de Dados e Engenheiros de Dados sobre o que é necessário para construir um modelo de sucesso.

---

### 1. Visão Geral

*   **Objetivo do Modelo:** Qual problema de negócio o modelo de IA irá resolver? (Copiar do PRD)
*   **Tarefa do Modelo:** Qual é a tarefa técnica do modelo? (Ex: Classificação binária, regressão, geração de texto)

### 2. Requisitos de Dados para Treinamento

| Seção | Descrição |
| :--- | :--- |
| **Fonte de Dados Ideal** | Descreva o dataset perfeito que você gostaria de ter. Quais são todas as colunas (features) e o que elas representam? |
| **Rótulo (Label) / Variável Alvo** | O que estamos tentando prever? Qual é a "resposta certa" que o modelo precisa aprender? (Ex: `is_churned`, `estimated_price`, `generated_summary`) |
| **Features (Variáveis de Entrada)** | Quais são os sinais ou atributos que o modelo usará para fazer a previsão? (Ex: `user_age`, `last_login_date`, `product_description`) |
| **Volume de Dados Necessário** | Qual é a estimativa de quantos exemplos (linhas) de dados precisamos para treinar um modelo viável? (Ex: 10.000 exemplos rotulados) |
| **Período Histórico** | Qual é o intervalo de tempo dos dados que precisamos? (Ex: Últimos 2 anos de dados de vendas) |

### 3. Disponibilidade e Coleta de Dados

*   **Fontes de Dados Atuais:**
    *   [**Fonte 1:** Ex: Banco de dados de produção (PostgreSQL)] - [**Tabelas Relevantes:** `users`, `orders`]
    *   [**Fonte 2:** Ex: Logs de eventos (Segment)] - [**Eventos Relevantes:** `product_viewed`, `add_to_cart`]
    *   [**Fonte 3:** Ex: Dados de terceiros (API do Salesforce)] - [**Objetos Relevantes:** `Lead`, `Opportunity`]

*   **Gap de Dados:**
    *   Quais dados necessários nós **NÃO** temos atualmente?
    *   **Plano de Ação para Coleta/Aquisição:**
        *   [**Dado Faltante 1:** Ex: Categoria do produto] - [**Ação:** Extrair via script a partir da descrição ou adicionar um novo campo no sistema.]
        *   [**Dado Faltante 2:** Ex: Rótulos de satisfação do cliente] - [**Ação:** Iniciar um projeto de rotulagem manual com uma ferramenta (ex: Labelbox) ou criar uma pesquisa no app para coletar feedback.]

### 4. Dicionário de Dados (Features e Rótulos)

Esta seção é crucial para evitar ambiguidades. Seja o mais explícito possível.

| Nome da Feature | Tabela/Origem | Tipo de Dado | Descrição Clara e Exemplo |
| :--- | :--- | :--- | :--- |
| `user_id` | `users` | `INTEGER` | Identificador único do usuário. Ex: `12345` |
| `order_amount` | `orders` | `FLOAT` | Valor total do pedido em Reais (BRL). Ex: `99.90` |
| `product_description` | `products` | `TEXT` | Descrição completa do produto. Ex: `"Camiseta de algodão com estampa..."` |
| `is_fraudulent` (Rótulo) | `orders` | `BOOLEAN` | `True` se o pedido foi confirmado como fraude, `False` caso contrário. |

### 5. Qualidade e Limpeza dos Dados

*   **Problemas de Qualidade Conhecidos:**
    *   [Ex: A coluna `user_age` tem muitos valores nulos ou com `0`.]
    *   [Ex: O formato da data na tabela `logs` é inconsistente.]
*   **Estratégia de Limpeza e Pré-processamento:**
    *   Como os valores ausentes serão tratados? (Ex: Preenchidos com a média, mediana, ou um valor constante)
    *   Como os dados categóricos serão transformados? (Ex: One-hot encoding)
    *   Como o texto será normalizado? (Ex: Lowercase, remoção de stopwords)

### 6. Requisitos de Rotulagem (Se Aplicável)

*   **Ferramenta de Rotulagem:** Qual ferramenta será usada? (Ex: Labelbox, V7, ou uma ferramenta interna)
*   **Instruções de Rotulagem:** Forneça um link para o guia detalhado para os rotuladores, com exemplos claros de casos positivos, negativos e de borda.
*   **Critérios de Qualidade:** Como a qualidade do trabalho dos rotuladores será medida? (Ex: Acordo inter-anotador, revisões de ouro).

### 7. Privacidade e Segurança

*   **Dados Sensíveis (PII):** O dataset contém informações de identificação pessoal? Quais colunas?
*   **Plano de Anonimização/Pseudonimização:** Qual é a estratégia para remover ou proteger esses dados antes de serem usados para treinamento? (Ex: Hashear `user_id`, remover colunas de nome e email).
*   **Controle de Acesso:** Quem terá acesso aos dados brutos e aos dados de treinamento?

### 8. Cronograma e Responsabilidades

| Atividade | Responsável | Data de Conclusão Estimada |
| :--- | :--- | :--- |
| Extração dos dados brutos | [Engenheiro de Dados] | [DD/MM/AAAA] |
| Projeto de Rotulagem | [Product Manager / Analista] | [DD/MM/AAAA] |
| Pipeline de Limpeza e Pré-processamento | [Cientista de Dados] | [DD/MM/AAAA] |
| Validação final do dataset de treinamento | [Cientista de Dados / PM] | [DD/MM/AAAA] |
