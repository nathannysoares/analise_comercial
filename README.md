# 📊 Dashboard Power BI - Análise de Vendas | Business Intelligence

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-326CE5?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

## 🎯 Objetivo do Projeto

Este projeto foi desenvolvido para demonstrar competências em:

- **Importação e tratamento de dados** de múltiplas fontes CSV
- **Desenvolvimento de medidas DAX**
- **Criação de visualizações** para responder perguntas de negócio específicas
- **Design de dashboard** executivo

---

## 📋 Perguntas de Negócio Respondidas

O dashboard foi construído para responder às seguintes questões estratégicas:

### 1️⃣ **Análise de Modos de Envio**
> *"Qual foi o total de valor venda considerando cada modo de envio dos pedidos?"*

**Gráfico Escolhido:** `Waterfall Chart (Cascata)`
- **Justificativa:** Visualiza a contribuição incremental de cada modo de envio
- **Insight:** Classe Padrão representa ~60% do volume total de vendas

### 2️⃣ **Custos Logísticos por Mercado**  
> *"Quais mercados tiveram o maior custo médio de envio dos produtos vendidos?"*

**Gráfico Escolhido:** `Treemap`
- **Justificativa:** Proporcionalidade visual clara entre mercados
- **Insight:** Canadá (17,78) apresenta melhor eficiência vs APAC (29,14)

### 3️⃣ **KPI de Performance de Vendas**
> *"Meta de manter média de 350 para valor de venda. Como está a performance em Abril/2014?"*

**Gráfico Escolhido:** `Gauge Chart (Velocímetro)`
- **Justificativa:** Visualização executiva imediata de performance vs meta
- **Resultado:** 246,49 (70,4% da meta) - **Performance sólida e recuperável**

### 4️⃣ **Lucratividade por Categoria**
> *"Considerando lucro = valor venda - custo envio, qual categoria apresentou maior lucro médio?"*

**Gráfico Escolhido:** `Donut Chart`
- **Justificativa:** Foco na categoria dominante sem ocupar muito espaço
- **Insight:** **Tecnologia domina com 46,55% do lucro** apesar de menor volume

### 5️⃣ **Evolução Temporal da Margem**
> *"Qual foi o comportamento da margem de lucro ao longo do tempo?"*

**Gráfico Escolhido:** `Line Chart (Série Temporal)`
- **Justificativa:** Padrão gold para análise de tendências temporais
- **Insight:** Recuperação consistente de 2013-2014, atingindo ~200M

---

## 📈 Principais Insights Descobertos

### 🎯 **Performance Geral**
- **KPI atual: 246,49** (70,4% da meta de 350)
- **Gap de apenas 29,6%** - meta facilmente atingível com ajustes táticos
- **Tendência de crescimento** consistente desde 2013

### 💡 **Oportunidades Estratégicas**

| Área | Insight | Ação Recomendada |
|------|---------|------------------|
| **📱 Categoria** | Tecnologia: 46,55% do lucro com menor volume | Expandir portfólio e marketing |
| **🚚 Logística** | Canadá 40% mais eficiente que APAC | Replicar modelo canadense |
| **📦 Envios** | Classe Padrão domina volume | Migrar clientes para modalidades premium |
| **📊 Mix** | Material Escritório: alto volume, baixa margem | Rebalancear mix de produtos |

### 🔄 **Evolução Temporal**
- **2011-2012:** Alta volatilidade (50-100M)
- **2013:** Período de baixa performance (~50M) 
- **2014:** **Recuperação robusta** atingindo ~200M
- **Tendência:** Crescimento sustentado pós-crise

---

## 📊 Estrutura dos Dados

### **Fontes de Dados Utilizadas**

Baseado nos arquivos CSV fornecidos pela Data Science Academy:

```
📋 DADOS DE ENTRADA:
├── 👥 Clientes.csv (1.590 registros)
│   ├── ID Cliente, Nome Cliente
│   ├── Segmento (Consumidor/Corporativo/Outros)
│   ├── Localização (Cidade, Estado, País)
│   └── Mercado (US/APAC/EU/LATAM)
│
├── 📦 Produtos.csv  
│   ├── ID Produto
│   ├── Categoria (Tecnologia/Móveis/Material Escritório)
│   ├── SubCategoria
│   └── Nome Produto
│
├── 📅 Pedidos.csv (25.036 registros)
│   ├── ID Pedido
│   ├── Data Pedido, Data Envio
│   ├── Modo Envio (Mesmo Dia/Primeira Classe/Segunda Classe/Classe Padrão)
│   └── Prioridade Pedido
│
└── 💰 Vendas.csv (transações principais)
    ├── Pedido, Cliente, Produto
    ├── Valor Venda
    ├── Quantidade Vendida
    └── Custo Envio
```

---

## ⚡ Medida DAX Implementada

### **Margem de Lucro**
```dax
MargemLucro = ROUND(DIVIDE(Vendas[Lucro],Vendas[Valor Venda]) * 100, 2)
```

**Análise da Implementação:**
- ✅ **DIVIDE()** com proteção automática contra divisão por zero
- ✅ **ROUND()** para precisão de 2 casas decimais
- ✅ **Multiplicação por 100** para formato percentual
- ✅ **Referência direta** às colunas da tabela Vendas

**Características Técnicas:**
- **Função DIVIDE()**: Evita erros de #DIV/0 em registros com vendas zeradas
- **Função ROUND()**: Padronização visual com controle de precisão  
- **Formato Percentual**: Multiplicação por 100 para melhor legibilidade
- **Performance Otimizada**: Cálculo eficiente em nível de linha (row context)

Esta implementação demonstra boas práticas de desenvolvimento DAX, priorizando robustez e legibilidade do código.

---

## 🎓 Competências Demonstradas

### **📊 Power BI**
- Importação de múltiplos arquivos CSV
- Criação de relacionamentos entre tabelas
- Desenvolvimento de visualizações específicas (Waterfall, Treemap, Gauge)
- Design de dashboard executivo

### **🔧 DAX (Data Analysis Expressions)**
- Criação de medidas customizadas
- Uso de funções de proteção (DIVIDE)
- Formatação e arredondamento de valores
- Cálculos percentuais

### **📈 Business Intelligence**
- Interpretação de requisitos de negócio
- Criação de KPIs relevantes
- Análise temporal de dados
- Comparação entre categorias e mercados

---

## 📁 Estrutura do Projeto

```
📂 powerbi-vendas-dashboard/
├── 📊 dashboard/
│   └── analise_comercial.pbix
├── 📋 data/
│   ├── Clientes.csv (1.590 registros)
│   ├── Pedidos.csv (25.036 transações)  
│   ├── Produtos.csv
│   └── Vendas.csv
└── 📄 images/
│   ├── dash_comercial.png
│   ├── tabelas_relacionadas

```

---

## 🚀 Como Reproduzir

### **Pré-requisitos**
- Microsoft Power BI Desktop
- Arquivos CSV fornecidos pela Data Science Academy

### **Passos**
1. **Importe os dados**
   - Conecte aos 4 arquivos CSV
   - Configure os relacionamentos entre as tabelas

2. **Crie a medida DAX**
   ```dax
   MargemLucro = ROUND(DIVIDE(Vendas[Lucro],Vendas[Valor Venda]) * 100, 2)
   ```

3. **Construa as visualizações**
   - Waterfall Chart para modos de envio
   - Treemap para custos por mercado
   - Gauge Chart para KPI (meta = 350)
   - Gráficos adicionais conforme necessário

4. **Responda às perguntas**
   - Valide se cada visual responde à pergunta correspondente
   - Ajuste formatação conforme necessário

---

## 👩‍💻 Sobre

Projeto desenvolvido por Nathanny Soares durante o curso de Power BI da Data Science Academy.

[🔗 LinkedIn]([https://www.linkedin.com](https://www.linkedin.com/in/nathannysoares/)) • [💻 GitHub](https://github.com/nathannysoares)

