# 💜 Dashboard – Avaliação da Feira de Projetos (Fluxar)

## 🧩 Introdução
No contexto da **Feira de Projetos**, foi desenvolvido um **dashboard avaliativo** para consolidar as notas e percepções dos avaliadores sobre o desempenho do projeto **Fluxar** em diferentes critérios:

- Apresentação do projeto  
- Apresentação do stand  
- Ideia usada para resolver o problema  
- Solução desenvolvida  

O painel foi criado com base nos dados coletados a partir das avaliações armazenadas em nosso banco de dados, e tem como objetivo **oferecer uma visão clara e interativa sobre o desempenho geral da equipe**, facilitando a análise de pontos fortes e oportunidades de melhoria.

---

## 🎯 Objetivo
O **dashboard de avaliação** foi projetado para ajudar a equipe a **monitorar e compreender o desempenho do projeto na feira**, com base nas notas atribuídas pelos avaliadores.  

Ele apresenta **indicadores de desempenho (cartões)**, **gráficos comparativos** e **filtros (slicers)**, permitindo uma análise detalhada por critério e por nota.  
O principal objetivo é **fornecer uma visão quantitativa e visual do desempenho**, apoiando decisões sobre como aprimorar futuras apresentações e soluções.

---

## 📊 Métricas do Visual

### 🟪 Cartões
| **Métrica** | **Significado** | **Conclusão Tirada** |
|--------------|-----------------|----------------------|
| **Melhor Nota** | Maior média ponderada entre os critérios avaliados. | A “Solução desenvolvida” apresentou o melhor desempenho geral. |
| **Média Ponderada** | Média geral das notas considerando peso por critério. | O projeto obteve **nota média 4,17**, indicando desempenho sólido. |
| **Qtd. Avaliações** | Total de respostas registradas no sistema. | Foram **12 avaliações**, garantindo diversidade de opinião. |
| **Desempenho (%)** | Percentual de aproveitamento em relação à nota máxima. | O desempenho geral foi **83,33%**, representando um resultado muito bom. |
| **Menor Nota** | Menor valor atribuído pelos avaliadores. | A menor nota foi **3,00**, indicando alguma divergência de percepção. |
| **Maior Nota** | Maior valor recebido nas avaliações. | A maior nota foi **5,00**, reforçando a qualidade em alguns critérios. |

---

## 🎛️ Slicers (Filtros)

| **Filtro** | **Significado** | **Conclusão Tirada** |
|-------------|----------------|----------------------|
| **grade_name** | Permite selecionar o critério de avaliação desejado (ex: Solução desenvolvida, Apresentação do stand). | Facilita a análise isolada de cada aspecto do projeto. |
| **score** | Filtra por notas atribuídas (de 3 a 5). | Ajuda a verificar a distribuição das avaliações e detectar variações de percepção. |
| **Limpar Segmentações** | Remove todos os filtros aplicados. | Permite retornar rapidamente à visão geral do dashboard. |

---

## 📈 Gráficos

### 📊 Qtd Avaliações por Score (Colunas)
Mostra quantas avaliações foram registradas para cada nota (3, 4 e 5).  
**Conclusão:** A maioria das notas atribuídas está entre **4 e 5**, reforçando um bom nível de satisfação geral.

---

### 📋 Média Ponderada por Critério (Barras Horizontais)
Apresenta a média ponderada para cada um dos critérios avaliados.  
**Conclusão:** As maiores médias foram obtidas em **Ideia usada para resolver o problema (4,3)** e **Solução desenvolvida (4,3)**, evidenciando destaque na proposta e na execução.

---

### 🍩 Qtd Avaliações por Score (Rosca)
Distribuição percentual das notas atribuídas.  
**Conclusão:** A maioria das avaliações foi de **nota 5 (50%)**, o que demonstra alta aprovação do público e dos avaliadores.

---

### 📊 Média Simples x Média Ponderada por Critério (Colunas)
Compara as médias simples e ponderadas para cada critério.  
**Conclusão:** A semelhança entre as médias mostra **consistência nas avaliações**, indicando equilíbrio entre os critérios.

---

### 🎯 % Desempenho por Critério (Rosca)
Representa a proporção do desempenho total de cada critério em relação ao resultado geral.  
**Conclusão:** Todos os critérios tiveram participação semelhante (**24–26%**), o que mostra **equilíbrio no desempenho do projeto**.

---