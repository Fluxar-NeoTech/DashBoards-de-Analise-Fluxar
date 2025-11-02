# 📊 Relatório Analítico — Dashboard Fluxar

## 🎯 Visão Geral
O **Dashboard Fluxar** tem como objetivo monitorar o **desempenho do fluxo de estoque** das indústrias cadastradas no sistema.  
Ele centraliza informações sobre **movimentação (entradas e saídas)**, **capacidade total e ocupação** dos estoques, além de permitir o acompanhamento da **eficiência operacional por unidade, produto e tipo**.

Os dados exibidos são provenientes principalmente das tabelas:

- `historico_estoque` — movimentações de entrada e saída;
- `historico_capacidade` — capacidade total e ocupada;
- `produto`, `unidade`, `industria`, `setor` — dimensões auxiliares de filtragem e contexto.

---

## 💠 Cartões / Métricas Principais

| Métrica | Fonte no Banco | Significado | Insight que Gera |
|----------|----------------|--------------|------------------|
| **Ocupação (%)** | `historico_capacidade.porcentagem_ocupacao` | Percentual de espaço utilizado no estoque em relação à capacidade máxima. | Permite identificar se há **sobrecarga ou ociosidade** nas unidades. Valores acima de 80% podem indicar risco de superlotação. |
| **Capacidade Total (m³)** | `capacidade_estoque.capacidade_maxima` | Volume máximo que pode ser armazenado somando todos os setores e unidades. | Dá uma noção da **escala de operação da indústria**, útil para planejar expansão. |
| **Entrada (m³)** | `historico_estoque.volume_movimentado` filtrando `movimentacao = 'E'` | Volume total que entrou no período. | Mostra o **nível de reabastecimento** — entradas elevadas podem indicar aumento de produção ou nova remessa. |
| **Saída (m³)** | `historico_estoque.volume_movimentado` filtrando `movimentacao = 'S'` | Volume total que saiu no período. | Indica **demanda e consumo** — picos de saída podem sinalizar vendas altas ou desperdício. |
| **Volume Ocupado (m³)** | `historico_capacidade.capacidade_total_ocupada` | Soma atual de volumes armazenados. | Ajuda a visualizar o **espaço real ocupado**, acompanhando a capacidade em tempo real. |

Esses cartões fornecem uma **visão executiva resumida**, permitindo aos gestores identificar rapidamente a situação operacional do estoque.

---

## 🎛️ Slicers (Filtros)

| Filtro | Tabela Base | Função | Importância Analítica |
|---------|--------------|--------|-----------------------|
| **Indústria** | `industria` | Permite visualizar apenas os dados de uma empresa específica. | Ajuda a comparar desempenho entre diferentes indústrias que utilizam o sistema. |
| **Unidade** | `unidade` | Seleciona filiais ou locais específicos. | Facilita o **diagnóstico local**, identificando unidades com ocupação acima da média. |
| **Setor** | `setor` | Filtra produtos e capacidades por área (limpeza, higiene, alimentos etc.). | Essencial para **detectar gargalos operacionais** e planejar redistribuição de espaço. |
| **Movimentação (Entrada/Saída)** | `historico_estoque.movimentacao` | Alterna entre análises de entrada, saída ou ambas. | Ajuda a **comparar o fluxo logístico**, avaliando o equilíbrio entre entradas e saídas. |

Esses slicers tornam o dashboard **interativo e adaptável**, permitindo análises sob diferentes perspectivas (empresa, unidade, setor ou produto).

---

## 📊 Gráficos e Indicadores Visuais

### 1️⃣ Movimentação por Mês
- **Base:** `historico_estoque.data`, `historico_estoque.volume_movimentado`
- **Descrição:** Linha temporal com a soma dos volumes movimentados ao longo do tempo.
- **Conclusão:** Permite observar **sazonalidade e picos de movimentação**, úteis para prever períodos de alta demanda e planejar reabastecimento.

---

### 2️⃣ Volume Total de Estoque por Tipo
- **Base:** `produto.tipo` + `historico_capacidade.capacidade_total_ocupada`
- **Descrição:** Gráfico de barras horizontais com o volume total armazenado por categoria (Bebida, Alimento, Higiene, Limpeza...).
- **Conclusão:** Ajuda a **identificar quais tipos de produtos ocupam mais espaço** e se o estoque está sendo distribuído de forma equilibrada entre as categorias.

---

### 3️⃣ Volume Movimentado (Donut)
- **Base:** `historico_estoque.movimentacao` (‘E’ / ‘S’)
- **Descrição:** Gráfico de rosca mostrando o percentual de volume movimentado entre **entradas (E)** e **saídas (S)**.
- **Conclusão:** Indica o **equilíbrio do fluxo logístico** — se o estoque está crescendo, se mantendo ou diminuindo.

---

### 4️⃣ Movimentação de Produtos
- **Base:** `produto.nome`, `historico_estoque.volume_movimentado`
- **Descrição:** Barras verticais com os produtos mais movimentados.
- **Conclusão:** Destaca **os produtos com maior rotatividade**, permitindo decisões mais assertivas sobre compras, produção e controle de estoque.

---

### 5️⃣ Ocupação por Nome e Nome (Unidade x Produto)
- **Base:** `unidade.nome`, `historico_capacidade.porcentagem_ocupacao`
- **Descrição:** Gráfico de barras comparando o nível de ocupação das unidades, categorizado por produto.
- **Conclusão:** Facilita a identificação de **unidades sobrecarregadas ou subutilizadas**, auxiliando no **equilíbrio da capacidade operacional**.

---

## 📈 Conclusões Gerais

| Perspectiva | Insight |
|--------------|----------|
| **Operacional** | As métricas permitem avaliar se as operações logísticas estão equilibradas (entradas ≈ saídas). |
| **Espacial** | O gráfico de ocupação mostra claramente se há necessidade de **expansão de armazéns** ou reorganização dos setores. |
| **Financeira** | O percentual de ocupação e o volume movimentado podem ser correlacionados com o plano contratado (`plano.preco`, `duracao_meses`), avaliando o **custo-benefício** da operação. |
| **Gestão de Produto** | Os produtos com maior movimentação devem ter **reposição automatizada** ou **monitoramento via RPA**, reduzindo rupturas e desperdícios. |
| **Tomada de Decisão** | O dashboard oferece uma **visão integrada e orientada a dados**, apoiando tanto decisões estratégicas (nível executivo) quanto operacionais (nível analista). |

---

✨ **Conclusão Final:**  
O Dashboard Fluxar integra informações críticas sobre estoque, movimentações e capacidade, proporcionando uma **visão completa e inteligente** do desempenho industrial.  
Ele fortalece a **gestão baseada em dados (Data-Driven)** e torna o acompanhamento operacional mais ágil, confiável e visualmente acessível.

---
