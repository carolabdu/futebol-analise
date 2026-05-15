# Manchester City 2020/21 — Análise de Dados

## Descrição

Análise estatística aprofundada do elenco do **Manchester City** na temporada 2020/21, utilizando dados das 5 principais ligas europeias extraídos via **FBRef/Fbstats**. 

Este projeto busca:
- **Identificar perfis táticos** dos jogadores por posição
- **Normalizar métricas** através de índices compostos (Min-Max 0→1)
- **Visualizar padrões** em gráficos interativos (Plotly)
- **Encontrar substitutos** com características similares no mercado (scouting)

O foco é em análise *por 90 minutos* para comparabilidade entre jogadores com tempos distintos de atuação.

---

## Estrutura do Projeto

```
0-Trabalho.ipynb              # Notebook principal — análise completa por posição
Analise_City_20_21.ipynb      # Notebook complementar — análise específica
Analise_City_20_21_soccerdata.ipynb  # Análise com dados SoccerData
data.csv                      # Dataset com 5 principais ligas europeias (2020/21)
metrics.txt                   # Lista de 128 colunas disponíveis
columns_description.md        # Descrição detalhada de cada métrica
requirements.txt              # Dependências Python (Pandas, Plotly, NumPy, etc.)
Understat/                    # Dados JSON de eventos brutos por partida
  ├── league_1_season_2020.json
  ├── match_*.json            # ~100 arquivos com eventos de cada jogo
  └── leagues.json
README.md                     # Este arquivo
```

---

## Dataset

### Fonte e Cobertura
- **Fonte primária:** FBRef via Fbstats (métricas estatísticas agregadas por 90 minutos)
- **Fonte alternativa:** Understat (dados brutos de eventos e ações por partida — JSON)
- **Temporada:** 2020/21 (ago/2020 até mai/2021)
- **Ligas cobertas:** 
  - 🏴󠁧󠁢󠁥󠁮󠁧󠁿 Premier League (England)
  - 🇪🇸 La Liga (Spain)
  - 🇩🇪 Bundesliga (Germany)
  - 🇮🇹 Serie A (Italy)
  - 🇫🇷 Ligue 1 (France)

### Especificações
- **Filtro aplicado:** jogadores com **> 500 minutos jogados** (reduz ruído de backup players)
- **Total de colunas:** 128
  - 6 colunas de identificação (nome, clube, posição, idade, nacionalidade, minutos)
  - 122 colunas de estatísticas normalizadas (por 90 min)
- **Variáveis cobertas:**
  - Estatísticas ofensivas (gols, xG, assistências, passes progressivos)
  - Defesa e recuperação de bola (desarmes, bloqueios, pressões)
  - Posse e distribuição (% posse, passes completados, turnover)
  - Pressão e intensidade (pressões, duelos aéreos, faltas)
- **Referência de métricas:** https://x.com/ronanmann/status/1408504415690969089

---

## Metodologia

A análise estrutura-se em **três componentes principais** aplicados por posição:

### 1. Métricas Extraídas
Seleção de colunas diretamente do dataset (data.csv) mais relevantes para cada posição, priorizando:
- Clareza de interpretação
- Variância explicativa dentro da posição
- Alinhamento com o modelo de jogo do Manchester City (posse alta, pressing, construção ofensiva)

### 2. Índices Calculados
Combinação de 2-4 métricas normalizadas (Min-Max 0→1 por posição) para criar **indicadores táticos compostos**, exemplo:
- **Índice de Pressão** = (Pressões + Duelos Aéreos) / 2 [normalizado]
- **Índice de Verticalidade** = (Passes Progressivos + xA) / 2 [normalizado]
- **Índice de Eficiência Defensiva** = (Desarmes + Bloqueios) / (Faltas) [normalizado]

Isso reduz dimensionalidade e melhora a interpretabilidade tática.

### 3. Visualizações Interativas
Todos os gráficos em **Plotly Express/Graph Objects** com funcionalidades:
- Hover para detalhes de jogador
- Zoom e pan para exploração
- Download como PNG
- Quadrantes com linhas de média/mediana

---

### Posições Analisadas

| Posição | Foco Principal | Métricas-Chave |
|---|---|---|
| **GK** | Saída de bola, distribuição, organização defensiva | % passes completados, passes progressivos, duelos aéreos, distribuição territorial |
| **DF** (zagueiros/laterais) | Eficiência defensiva, progressão, ocupação de espaço | Desarmes, bloqueios, pressões, passes progressivos, cobertura territorial |
| **MF** (meias/volantes) | Criatividade, pressão, segurança, transição | Assistências, xA, pressões, passes completados, turnover recovery |
| **FW** (avançados/extremos) | Finalização, pressing, progressão direta | Gols, xG, pressões, toques na área, passes progressivos |

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

## Como Executar

### Pré-requisitos
- Python 3.8+
- pip ou conda

### Instalação e Execução

```bash
# 1. Instalar dependências
pip install -r requirements.txt

# 2. Abrir o notebook no Jupyter Notebook
jupyter notebook 0-Trabalho.ipynb

# Ou usar Jupyter Lab (recomendado para interatividade)
jupyter lab 0-Trabalho.ipynb
```

### Notebooks Disponíveis
- **0-Trabalho.ipynb** — Análise principal (recomendado iniciar aqui)
- **Analise_City_20_21.ipynb** — Análise alternativa com foco em comparativas
- **Analise_City_20_21_soccerdata.ipynb** — Análise com dados SoccerData (eventos)

---

## Próximos Passos

- [ ] Aplicar clustering (k-means) para encontrar jogadores similares no dataset completo
- [ ] Normalizar métricas por posição para comparação cross-positional
