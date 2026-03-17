# FarmTech Solutions — Análise de Rendimento de Safras

**FIAP | Fase 5 — Cap 1 - FarmTech na Era da Cloud Computing**
**Aluno:** Diogo Gose | **RM:** 566951

---

## Sobre o Projeto

Este projeto foi desenvolvido para a **FarmTech Solutions**, empresa prestadora de serviços de IA para uma fazenda de médio porte de 200 hectares que cultiva múltiplas culturas agrícolas.

O objetivo é analisar dados de condições climáticas e solo para:

- Realizar uma **análise exploratória** dos dados de rendimento de safra;
- Identificar **tendências e clusters** de produtividade, incluindo detecção de outliers;
- Construir e comparar **5 modelos preditivos** de regressão para estimar o rendimento por hectare.

---

## Dataset

O arquivo `database/crop_yield.csv` contém 156 registros de 4 culturas com as seguintes variáveis:

| Coluna | Descrição |
|---|---|
| `Crop` | Cultura agrícola (Cocoa beans, Oil palm fruit, Rice paddy, Rubber natural) |
| `Precipitation (mm day-1)` | Precipitação diária em milímetros |
| `Specific Humidity at 2 Meters (g/kg)` | Umidade específica a 2 m acima do solo |
| `Relative Humidity at 2 Meters (%)` | Umidade relativa a 2 m acima do solo |
| `Temperature at 2 Meters (C)` | Temperatura em °C a 2 m acima do solo |
| `Yield` | Rendimento da safra em ton/ha — **variável alvo** |

---

## Estrutura do Repositório

```
database/
│   └── crop_yield.csv
├── DiogoGose_rm566951_pbl_fase5.ipynb   ← Notebook principal
└── README.md
```

---

## Conteúdo do Notebook

O notebook está organizado nas seguintes seções:

1. **Setup e Importações** — carregamento de bibliotecas
2. **Análise Exploratória (EDA)** — inspeção, distribuições, correlações e visualizações por cultura
3. **Clusterização (ML Não Supervisionado)** — K-Means com Elbow Method, Silhouette Score, visualização PCA e detecção de outliers via Isolation Forest
4. **Modelagem Preditiva (ML Supervisionado)** — 5 algoritmos de regressão (Linear Regression, Decision Tree, Random Forest, Gradient Boosting, SVR) com tabela comparativa de métricas e análise de resíduos
5. **Conclusões** — achados, recomendações para a FarmTech Solutions e limitações do trabalho

---

## Demonstração em Vídeo

> **Link do vídeo (YouTube):** `https://youtu.be/l7IB0pZt0fQ`

## Link do jupyter notebook

> **jupyter notebook:** `https://colab.research.google.com/drive/1peOULPTFNBJ1ShCoDef2NRpXWDpSWE1h?usp=sharing`
