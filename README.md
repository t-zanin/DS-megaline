#### (Portuguese version below)

# Megaline Telecom Revenue Analysis

## Project Overview

This project analyzes customer behavior and revenue generation for Megaline, a telecommunications company offering two prepaid plans: **Surf** and **Ultimate**. The goal is to determine which plan generates more revenue to optimize the company’s advertising budget. Based on a sample of 500 customers, the analysis examines call, text, and data usage patterns in 2018 to identify revenue trends and provide actionable insights.

## Objectives

- Analyze customer behavior for the Surf and Ultimate plans.
- Calculate monthly usage (calls, messages, and data) and revenue per user.
- Compare average revenue between the two plans.
- Investigate regional revenue differences, focusing on the NY-NJ area.
- Provide recommendations for marketing and pricing strategies based on the findings.

## Data Description

The dataset consists of five tables:

1. **users**: Information about 500 customers, including user ID, name, age, registration date, churn date, city, and plan type.
2. **calls**: Call records with call ID, date, duration, and user ID.
3. **messages**: Text message records with message ID, date, and user ID.
4. **internet**: Web session records with session ID, data usage (MB), date, and user ID.
5. **plans**: Plan details, including monthly fees, included minutes, messages, and data, along with overage charges.

### Plan Details
- **Surf**:
  - Monthly fee: $20
  - Includes: 500 minutes, 50 messages, 15 GB of data
  - Overage charges: $0.03/min, $0.03/message, $10/GB
- **Ultimate**:
  - Monthly fee: $70
  - Includes: 3,000 minutes, 1,000 messages, 30 GB of data
  - Overage charges: $0.01/min, $0.01/message, $7/GB

*Note*: Call durations are rounded up to the nearest minute, and monthly data usage is rounded up to the nearest GB.

## Data Preprocessing

- **Data Types**:
  - The columns `reg_date` and `churn_date` (users), `call_date` (calls), `message_date` (messages), and `session_date` (internet) were converted from string to DateTime.
- **Missing Values**:
  - In the `users` table, 466 missing values in `churn_date` (active customers) were replaced with a fixed future date.
- **Data Quality**:
  - No duplicates or missing values were found in the `calls` (137,735 rows), `messages` (76,051 rows), and `internet` (104,825 rows) tables.
  - Column names were checked for consistency, with no uppercase letters or spaces.

## Analysis Steps

1. **Data Aggregation**:
   - Monthly usage per user was calculated for calls (minutes), messages, and data (MB).
   - Monthly revenue per user was computed by subtracting plan limits, applying overage rates, and adding the monthly fee.
2. **Descriptive Statistics**:
   - Mean, variance, and standard deviation were calculated for minutes, messages, and data usage by plan.
   - Distributions were visualized using histograms and box plots.
3. **Hypothesis Testing**:
   - Tested whether average revenue differs between the Surf and Ultimate plans.
   - Compared average revenue of NY-NJ users with other regions.
4. **Visualizations**:
   - Box plots revealed outliers in usage for both plans, with a slight advantage for Surf.
   - Histograms showed higher frequency of messages in Surf (especially up to 60 messages) and significantly higher data usage in Surf compared to Ultimate.

## Key Findings

- **Plan Comparison**:
  - The **Surf** plan, despite its lower cost, generates significant revenue due to frequent overage purchases (minutes, messages, and data).
  - The **Ultimate** plan generates higher revenue per user due to its higher base fee and additional benefits, though users rarely exceed plan limits.
- **Usage Patterns**:
  - Surf users, often younger, tend to use more data and messages, requiring additional packages.
  - Ultimate users consume resources more conservatively, staying within plan limits.
- **Regional Insights**:
  - NY-NJ users generate less revenue compared to other regions, suggesting the need for adjustments in marketing or pricing.

## Conclusions and Recommendations

- **Revenue Contribution**:
  - The Ultimate plan is more profitable due to its higher base price and stable revenue.
  - The Surf plan plays a key role in attracting high-usage customers who generate revenue through overage purchases.
- **Marketing Strategy**:
  - Promote the Surf plan to younger audiences with high demand for data and messaging.
  - Highlight the value of the Ultimate plan for customers seeking predictability and higher limits.
- **Regional Focus**:
  - Conduct a detailed study of NY-NJ user profiles to understand the lower revenue and adjust marketing or pricing strategies.
- **Business Impact**:
  - Balancing both plans is essential: Surf attracts volume due to affordability, while Ultimate ensures stable, high-margin revenue.

## Tools and Technologies

- **Language**: Python
- **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, SciPy (for statistical tests)
- **Environment**: Jupyter Notebook

## Project Structure

- `notebooks/`: Jupyter Notebook with preprocessing, analysis, and visualizations.
- `data/`: Data files (not included in the repository due to size).
- `README.md`: Project overview and documentation.

____________________________________
____________________________________
____________________________________
____________________________________


Versão em português

# Análise de Receita da Megaline Telecom

## Visão Geral do Projeto

Este projeto analisa o comportamento dos clientes e a geração de receita da Megaline, uma empresa de telecomunicações que oferece dois planos pré-pagos: **Surf** e **Ultimate**. O objetivo é determinar qual plano gera mais receita para otimizar o orçamento de publicidade da empresa. Com base em uma amostra de 500 clientes, a análise examina padrões de uso de chamadas, mensagens e dados em 2018 para identificar tendências de receita e fornecer insights acionáveis.

## Objetivos

- Analisar o comportamento dos clientes dos planos Surf e Ultimate.
- Calcular o uso mensal (chamadas, mensagens e dados) e a receita por usuário.
- Comparar a receita média entre os dois planos.
- Investigar diferenças regionais de receita, com foco na área de NY-NJ.
- Fornecer recomendações para estratégias de marketing e preços com base nos resultados.

## Descrição dos Dados

O conjunto de dados é composto por cinco tabelas:

1. **users**: Informações sobre 500 clientes, incluindo ID do usuário, nome, idade, data de registro, data de churn, cidade e tipo de plano.
2. **calls**: Registros de chamadas com ID da chamada, data, duração e ID do usuário.
3. **messages**: Registros de mensagens de texto com ID da mensagem, data e ID do usuário.
4. **internet**: Registros de sessões web com ID da sessão, uso de dados (MB), data e ID do usuário.
5. **plans**: Detalhes dos planos, incluindo taxas mensais, minutos, mensagens e dados incluídos, além de tarifas de excedentes.

### Detalhes dos Planos
- **Surf**:
  - Taxa mensal: $20
  - Inclui: 500 minutos, 50 mensagens, 15 GB de dados
  - Tarifas de excedente: $0,03/minuto, $0,03/mensagem, $10/GB
- **Ultimate**:
  - Taxa mensal: $70
  - Inclui: 3.000 minutos, 1.000 mensagens, 30 GB de dados
  - Tarifas de excedente: $0,01/minuto, $0,01/mensagem, $7/GB

*Observação*: A duração das chamadas é arredondada para o minuto superior, e o uso de dados mensal é arredondado para o GB superior.

## Pré-processamento dos Dados

- **Tipos de Dados**:
  - As colunas `reg_date` e `churn_date` (users), `call_date` (calls), `message_date` (messages) e `session_date` (internet) foram convertidas de string para DateTime.
- **Valores Ausentes**:
  - Na tabela `users`, 466 valores ausentes em `churn_date` (clientes ativos) foram substituídos por uma data futura fixa.
- **Qualidade dos Dados**:
  - Não foram encontrados duplicatas ou valores ausentes nas tabelas `calls` (137.735 linhas), `messages` (76.051 linhas) e `internet` (104.825 linhas).
  - Os nomes das colunas foram verificados como consistentes, sem letras maiúsculas ou espaços.

## Etapas da Análise

1. **Agregação de Dados**:
   - Calculado o uso mensal por usuário para chamadas (minutos), mensagens e dados (MB).
   - Computada a receita mensal por usuário subtraindo os limites do plano, aplicando tarifas de excedente e somando a taxa mensal.
2. **Estatísticas Descritivas**:
   - Calculadas média, variância e desvio padrão para minutos, mensagens e uso de dados por plano.
   - Visualizadas as distribuições com histogramas e diagramas de caixa.
3. **Testes de Hipóteses**:
   - Testado se a receita média difere entre os planos Surf e Ultimate.
   - Comparada a receita média dos usuários de NY-NJ com outras regiões.
4. **Visualizações**:
   - Diagramas de caixa revelaram valores atípicos no uso em ambos os planos, com leve vantagem para o Surf.
   - Histogramas mostraram maior frequência de mensagens no Surf (especialmente até 60 mensagens) e uso de dados significativamente maior no Surf em comparação com o Ultimate.

## Principais Descobertas

- **Comparação dos Planos**:
  - O plano **Surf**, apesar do custo menor, gera receita significativa devido à compra frequente de pacotes excedentes (minutos, mensagens e dados).
  - O plano **Ultimate** gera maior receita por usuário devido à taxa mensal mais alta e benefícios adicionais, embora os usuários raramente excedam os limites do plano.
- **Padrões de Uso**:
  - Usuários do Surf, frequentemente mais jovens, apresentam maior uso de dados e mensagens, exigindo pacotes adicionais.
  - Usuários do Ultimate consomem recursos de forma mais conservadora, mantendo-se dentro dos limites do plano.
- **Insights Regionais**:
  - Usuários de NY-NJ geram receita menor em comparação com outras regiões, sugerindo a necessidade de ajustes em marketing ou preços.

## Conclusões e Recomendações

- **Contribuição de Receita**:
  - O plano Ultimate é mais lucrativo devido ao preço base mais alto e receita estável.
  - O plano Surf desempenha um papel crucial ao atrair clientes de alto uso que geram receita por meio de compras de pacotes excedentes.
- **Estratégia de Marketing**:
  - Promover o plano Surf para públicos jovens com alta demanda por dados e mensagens.
  - Destacar o valor do plano Ultimate para clientes que buscam previsibilidade e limites mais altos.
- **Foco Regional**:
  - Realizar um estudo detalhado do perfil dos usuários de NY-NJ para entender a menor receita e ajustar estratégias de marketing ou preços.
- **Impacto no Negócio**:
  - Equilibrar os dois planos é essencial: o Surf atrai volume por ser acessível, enquanto o Ultimate garante receita estável e de alta margem.

## Ferramentas e Tecnologias

- **Linguagem**: Python
- **Bibliotecas**: Pandas, NumPy, Matplotlib, Seaborn, SciPy (para testes estatísticos)
- **Ambiente**: Jupyter Notebook

## Estrutura do Projeto

- `notebooks/`: Notebook Jupyter com pré-processamento, análise e visualizações.
- `data/`: Arquivos de dados (não incluídos no repositório devido ao tamanho).
- `README.md`: Visão geral e documentação do projeto.

