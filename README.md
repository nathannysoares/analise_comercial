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

O dashboard foi construído para responder às seguintes questões:

### 1️⃣ **Análise de Modos de Envio**
> *"Qual foi o total de valor venda considerando cada modo de envio dos pedidos?"*

**Gráfico Solicitado:** `Waterfall Chart (Cascata)`

### 2️⃣ **Custos Logísticos por Mercado**  
> *"Quais mercados tiveram o maior custo médio de envio dos produtos vendidos?"*

**Gráfico Solicitado:** `Treemap`

### 3️⃣ **KPI de Performance de Vendas**
> *"A empresa tem como objetivo (meta) manter uma média de 350 para o valor de venda todos os meses. Mostre um indicador (KPI) com o valor médio de venda. A empresa ficou abaixo ou acima da meta no mês de Abril/2014?"*

**Gráfico Solicitado:** `Gauge Chart (Velocímetro)`
**Meta Definida:** 350

### 4️⃣ **Lucratividade por Categoria**
> *"Considere que o lucro é equivalente a: valor venda - custo envio. Qual categoria de produto apresentou maior lucro médio?"*

**Análise:** Comparação entre Tecnologia, Móveis e Material de Escritório

### 5️⃣ **Evolução Temporal da Margem**
> *"Qual foi o comportamento da margem de lucro ao longo do tempo? Considere a margem de lucro como o lucro dividido pelo valor venda."*

**Gráfico:** Série temporal mostrando evolução da margem

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

**💡 Projeto desenvolvido como exercício prático do curso Power BI da Data Science Academy**
