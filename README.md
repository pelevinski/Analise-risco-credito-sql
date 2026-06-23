### **# Análise de Risco de Crédito e Previsão de Inadimplência com SQL e Python**

##### 

### **📝 Contexto do Projeto**

Este projeto simula um cenário real do mercado financeiro, onde uma instituição bancária necessita avaliar o perfil de seus clientes para entender os fatores que mais geram inadimplência (**loan\_status = 1**). O objetivo é identificar padrões comportamentais e financeiros para apoiar a tomada de decisão da diretoria de riscos, mitigando prejuízos financeiros.



Os dados passaram por uma etapa de extração e tratamento inicial em Python, e a modelagem final, armazenamento e análise exploratória profunda foram realizados localmente utilizando o banco de dados **PostgreSQL**.



\---

### **🛠️ Tecnologias e Ferramentas**

\* **Python (Pandas):** Limpeza de dados brutos e tratamento de valores nulos/outliers (Google Colab).

\* **PostgreSQL (v18):** Armazenamento de dados, modelagem de tabelas e consultas analíticas (Ambiente Local/Localhost).

\* **Análise de Risco de Crédito e Previsão de Inadimplência com SQL e Python**



\---

### **📂 Estrutura do Repositório**

\* **`limpeza\_dados\_credit.ipynb`/`limpeza\_dados\_credit.py`:** Contém o script Python utilizado no tratamento inicial do dataset.

\* **`SELECT.txt`:** Arquivo contendo todos os scripts de criação de tabelas e queries de negócios executadas no pgAdmin.

\* `**README.md`:** Relatório executivo com os insights de negócio gerados pelo projeto.



\---

#### 

### **📊 Principais Insights de Negócio**



##### **# 1. Visão Geral: Perfil de Renda e Alavancagem**

Ao agrupar os clientes por status de adimplência, identificamos um "Efeito Tesoura" clássico no risco de crédito:

\* **Clientes Adimplentes (0):** Apresentam uma renda anual média significativamente maior (**R$ 70.799,60**) e solicitam empréstimos de menor valor médio (**R$ 9.237,04**).

\* **Clientes Inadimplentes (1):** Possuem renda anual média menor (**R$ 49.124,26)**, mas solicitam valores de crédito maiores (**R$ 10.847,10**).

\* **Fator Idade:** A idade média de ambos os grupos é idêntica (**27 anos)**, provando que o risco não está associado à faixa etária, mas puramente à capacidade financeira.



##### **# 2. Risco por Finalidade do Empréstimo (loan\_intent)**

A análise percentual de calotes por categoria revelou quais intenções de uso do dinheiro trazem maior risco para o portfólio do banco:

\* **Maior Risco:** \[Consolidação de dívidas com 28.59%]

\* **Menor Risco:** \[Capital de risco com 14.81%]



##### **# 3. O Impacto da Moradia no Comportamento de Crédito**

Cruzando o tipo de moradia (**person\_home\_ownership**) com a inadimplência, descobrimos que clientes que moram de \[**Aluguel**] possuem uma taxa de calote de \[**31.57%**], enquanto proprietários de imóveis quitados representam o menor risco.



##### **# 4. Reincidência e Histórico de Negativação**

Clientes que já possuíam histórico prévio de inadimplência registrado (**cb\_person\_default\_on\_file = 'Y'**) apresentaram uma taxa de novos calotes de \[**37.80%**], validando a importância do uso de bureaus de crédito clássicos para a negação ou encarecimento da taxa de juros para esse público.



\---



### **📈 Conclusão e Recomendações Estratégicas**

Com base nas análises extraídas do banco de dados, as recomendações para a Diretoria de Riscos são:

1\. Políticas de Margem de Consignação: Restringir a concessão de crédito para clientes cuja relação Empréstimo/Renda ultrapasse o teto saudável identificado na análise.

2\. Precificação por Risco (Risk-Based Pricing): Aumentar a taxa de juros para as finalidades de alto risco (**Consolidação de dívidas**) para compensar a probabilidade de inadimplência.

3\. Bloqueio Automático por Histórico: Implementar uma regra de corte rígida para clientes com histórico 'Y' (**cb\_person\_default\_on\_file**), uma vez que a taxa de reincidência se provou acentuada.



\---


###### **Projeto desenvolvido de forma 100% privada e local, focado em Engenharia e Análise de Dados para o setor financeiro.**

