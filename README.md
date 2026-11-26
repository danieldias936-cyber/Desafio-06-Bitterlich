<div align="center">

# 🌲 Desafio 06 — Amostragem de Bitterlich

**Inventário por pontos de área basal no talhão 20**

![R](https://img.shields.io/badge/R-4.3-276DC3?logo=r&logoColor=white) ![Disciplina](https://img.shields.io/badge/Mensura%C3%A7%C3%A3o%20Florestal-ICA%2FUFMG-2E7D32) ![Semestre](https://img.shields.io/badge/semestre-2026%2F2-6D4C41) ![Status](https://img.shields.io/badge/status-conclu%C3%ADdo%20(dados%20n%C3%A3o%20inclu%C3%ADdos)-yellow)

*Disciplina Mensuração Florestal · Programa de Pós-Graduação em Ciências Florestais · ICA/UFMG*

</div>

> [!NOTE]
> A planilha de campo `bitterlich_talhao20.xlsx` não está no repositório. Para reproduzir a análise, coloque-a em `dados/`. As saídas já processadas estão em `resultados/tabelas/`.

## 📋 Objetivo

Processar um inventário por amostragem de Bitterlich, estimar o volume por hectare, o erro de amostragem e o volume total do talhão, e discutir as limitações de usar modelos ajustados em outro talhão.

## 🗂️ Dados

| Variável | Valor |
|---|---|
| Talhão | 20 (25 ha) |
| Fator de área basal (FAB) | 3 m²/ha |
| Pontos | 25, em grade de 100 × 100 m |
| Árvores contadas | 228 |

## 🔧 Métodos

- Árvores por hectare representadas por árvore contada: Nᵢ = FAB / gᵢ.
- Altura pela relação hipsométrica do [Desafio 02](https://github.com/danieldias936-cyber/desafio_altura) e volume pela equação de Spurr do [Desafio 04](https://github.com/danieldias936-cyber/desafio-04-volume-reduzido-e-tabela).
- Volume por ponto Vₕₐ = Σ Nᵢ · Vᵢ e estimativas por amostragem aleatória simples (IC de 95%).

## 📈 Principais resultados

| Estimativa | Valor |
|---|:-:|
| Volume médio | **370,13 m³/ha** |
| Coeficiente de variação | 33,3% |
| Erro relativo | **13,76%** |
| IC 95% por hectare | 319,21 a 421,06 m³/ha |
| Volume total (25 ha) | **9.253,3 m³** |
| IC 95% do total | 7.980,2 a 10.526,4 m³ |

- O erro relativo fica acima do limite usual de 10%; seriam necessários cerca de 47 pontos para atingi-lo.
- Área basal de 27,36 m²/ha e 1.242 árvores/ha, como verificação independente.
- Trocar Spurr por Schumacher-Hall muda o volume em apenas −1,0%, bem menos que o erro amostral.

## 📁 Estrutura do repositório

```text
desafio-06-bitterlich/
├── dados/                              # colocar aqui bitterlich_talhao20.xlsx
├── scripts/
│   └── 01_inventario_bitterlich.R
├── resultados/
│   └── tabelas/
│       ├── arvores_processadas.csv
│       ├── resumo_por_ponto.csv
│       └── resumo_inventario.csv
└── docs/
    ├── relatorio.md
    └── metodologia_detalhada.md
```

## ▶️ Como executar

A partir da raiz do repositório:

```r
install.packages(c("readxl"))
```

```bash
Rscript scripts/01_inventario_bitterlich.R dados/bitterlich_talhao20.xlsx resultados/tabelas
```

O script lê área, FAB e número de pontos da aba `Info_Talhao`, então processa outros talhões no mesmo formato.

## 📄 Documentos

- 📊 [Relatório](docs/relatorio.md)
- 🔍 [Metodologia detalhada](docs/metodologia_detalhada.md)

## 🧭 Série de desafios

| # | Desafio | |
|:-:|---|:-:|
| 01 | [Diâmetro](https://github.com/danieldias936-cyber/desafio-diametro-eucalipto) | |
| 02 | [Altura e relação hipsométrica](https://github.com/danieldias936-cyber/desafio_altura) | |
| 03 | [Volume e forma](https://github.com/danieldias936-cyber/desafio_volume-e-forma) | |
| 04 | [Volume reduzido e equações de volume](https://github.com/danieldias936-cyber/desafio-04-volume-reduzido-e-tabela) | |
| 05 | [Taper e sortimento](https://github.com/danieldias936-cyber/desafio_taper_e_sortimento) | |
| **06** | **Amostragem de Bitterlich** | 📍 você está aqui |
| 07 | [Classificação de sítios florestais](https://github.com/danieldias936-cyber/desafio-07-classificacao-sitio) | |
| 08 | [Validação do índice de sítio](https://github.com/danieldias936-cyber/desafio-08) | |
| 09 | [Crescimento e produção (Clutter)](https://github.com/danieldias936-cyber/desafio-09) | |

## 👤 Autor

**Daniel Dias** · [@danieldias936-cyber](https://github.com/danieldias936-cyber)  
Mestrado em Ciências Florestais — ICA/UFMG, Montes Claros (MG)
