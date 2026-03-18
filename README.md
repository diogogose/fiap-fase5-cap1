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
├── crop_yield.csv
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



# Entrega 2 — Estimativa de Custos na AWS

**FIAP | Fase 5 — Cap 1 - FarmTech na Era da Cloud Computing**
**Aluno:** Diogo Gose | **RM:** 566951

---

Foi realizada uma estimativa de custos utilizando a [Calculadora de Preços da AWS](https://calculator.aws/#/estimate?id=ead9999733c5934c7d4453559e8862e0016ce435), comparando duas regiões.

---

## Configuração da Máquina Avaliada

| Parâmetro | Valor |
|---|---|
| Sistema Operacional | Linux |
| Instância | t4g.micro |
| vCPUs | 2 |
| Memória RAM | 1 GiB |
| Rede | Até 5 Gigabit |
| Armazenamento (EBS) | 50 GB |
| Estratégia de Preço | On-Demand — 100% utilizado/mês |
| Localização | Instâncias compartilhadas |

> A instância **t4g.micro** é a opção que melhor atende às especificações mínimas solicitadas nas duas regiões comparadas.

---

## Estimativa de Custos — Calculadora AWS

### Custo Mensal por Região

| Região | Código AWS | Custo Mensal (USD) | Custo Anual (USD) |
|---|---|---|---|
| Virgínia do Norte (EUA) | `us-east-1` | **$8,38** | **$100,58** |
| São Paulo (Brasil) | `sa-east-1` | $14,08 | $168,98 |
| **Diferença** | — | **+$5,70 (+68%)** | **+$68,40 (+68%)** |


---

## Qual a solução mais barata?

A região **Virgínia do Norte (`us-east-1`)** é a mais barata, custando **$8,38/mês** — uma economia de **68%** em relação à região de São Paulo ($14,08/mês).

Ao longo de 12 meses, a diferença acumulada seria de **$68,40 USD** (aproximadamente **R$ 400–420**, a depender da cotação do dólar).

---

## restrições legais para armazenamento no exterior
 
Apesar de **Virgínia do Norte ser financeiramente mais barata**, existem dois fatores críticos que favorecem **São Paulo**:

#### 1. Conformidade com a LGPD

A **Lei Geral de Proteção de Dados** impõe restrições à transferência internacional de dados pessoais. 

#### 2. Latência de Acesso

Sensores de campo enviam leituras com frequência alta. A latência média entre o Brasil e a região `us-east-1` é de **~120–150 ms**, enquanto a região `sa-east-1` (São Paulo) apresenta **~5–20 ms** para conexões brasileiras. Essa diferença impacta diretamente a capacidade de **acesso rápido e em tempo real** aos dados dos sensores.

### Decisão

> **Região escolhida: São Paulo (`sa-east-1`)**

A escolha pela região de São Paulo é justificada pelos seguintes pilares:

| Pilar | Justificativa |
|---|---|
| **Conformidade Legal** | Dados armazenados em território brasileiro atendem à LGPD sem necessidade de cláusulas contratuais adicionais |
| **Latência** | Menor latência (~5–20 ms) garante acesso rápido e confiável aos dados dos sensores em campo |


## Resumo Final

| Item | Valor |
|---|---|
| Instância escolhida | t4g.micro  |
| Região recomendada | São Paulo (`sa-east-1`) |
| Custo mensal estimado | $14,08 USD |
| Custo anual estimado | $168,98 USD |
| Motivo principal | LGPD + baixa latência para sensores brasileiros |

