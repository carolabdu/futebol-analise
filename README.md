# Manchester City 2020/21 — Análise de Dados

Análise estatística do elenco do Manchester City na temporada 2020/21, utilizando dados das 5 principais ligas europeias extraídos via **FBRef/Fbstats**.

O objetivo é identificar o perfil tático dos jogadores por posição e, como próximo passo, encontrar jogadores com características similares no mercado (scouting).

---

## Estrutura do Projeto

```
0-Trabalho.ipynb         # Notebook principal de análise
data.csv                 # Dataset com as 5 principais ligas europeias (2020/21)
metrics.txt              # Lista de todas as colunas disponíveis
columns_description.md   # Descrição detalhada de cada coluna
requirements.txt         # Dependências Python
README.md                # Este arquivo
```

---

## Dataset

- **Fonte:** FBRef via Fbstats (métricas por 90 minutos)
- **Temporada:** 2020/21
- **Ligas:** Premier League, La Liga, Bundesliga, Serie A, Ligue 1
- **Filtro aplicado:** jogadores com > 500 minutos jogados
- **Total de colunas:** 128 (identificação + estatísticas)
- **Referência de métricas:** https://x.com/ronanmann/status/1408504415690969089

---

## Metodologia

A análise é dividida por posição, com três componentes:

1. **Métricas extraídas** — colunas diretamente do dataset relevantes para a posição
2. **Índices calculados** — combinações normalizadas (Min-Max 0→1) que criam indicadores táticos
3. **Visualizações interativas** — todos os gráficos em Plotly

### Posições analisadas

| Posição | Foco principal |
|---|---|
| **GK** | Saída de bola, posicionamento, contribuição na construção |
| **DF** | Eficiência de desarme, distribuição territorial, progressão ofensiva |
| **MF** | Criatividade, pressão, segurança de posse, verticalidade |
| **FW** | Eficiência de finalização, pressing, estilo de progressão |

---

## Visualizações

Todos os gráficos são interativos via **Plotly Express / Graph Objects**.

| Gráfico | Uso |
|---|---|
| Scatter com quadrantes | Comparação em dois eixos com referência de média |
| Barras empilhadas horizontais | Distribuição territorial (desarmes / pressões) |
| Radar (Scatterpolar) | Comparação multidimensional de perfil tático normalizado |
| Bubble chart | Volume × qualidade (ex: toques sob pressão) |

---

## Como executar

```bash
pip install -r requirements.txt
jupyter notebook 0-Trabalho.ipynb
```

---

## Próximos Passos

- [ ] Aplicar clustering (k-means) para encontrar jogadores similares no dataset completo
- [ ] Normalizar métricas por posição para comparação cross-positional
