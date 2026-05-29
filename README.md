# 🛣️ Painel de Duplicações e Ampliações de Rodovias · RS

Painel interativo dos 4 blocos de obras de duplicação e ampliação de rodovias no Rio Grande do Sul, desenvolvido com Leaflet.js e dados geoespaciais processados em Python/GeoPandas.

---

## 🗺️ Acesso

**GitHub Pages:** `https://SEU-USUARIO.github.io/NOME-DO-REPO/`

**Local:** descompacte o ZIP, entre na pasta e rode:
```bash
python -m http.server 8000
```
Depois acesse `http://localhost:8000` no navegador.

---

## 📦 Blocos de Concessão

| Bloco | Concessionária | Rodovias principais |
|-------|---------------|---------------------|
| Bloco 1 | EGR | ERS-020, ERS-040, ERS-115, ERS-118, ERS-235, ERS-239, ERS-474, ERS-010 |
| Bloco 2 | EGR | ERS-128, ERS-129, ERS-130, ERS-135, ERS-324, RSC-453 |
| Bloco 3 | CSG | ERS-122, ERS-240, ERS-446, RSC-287, RSC-453, BRS-470 |
| Bloco 4 | SACYR | RSC-287 (ST1 a ST11) |

---

## ✨ Funcionalidades

- **Filtro por bloco** — seleciona Todos / Bloco 1 / Bloco 2 / Bloco 3 (CSG) / Bloco 4 (SACYR)
- **Filtro por camada** — liga/desliga cada camada individualmente
- **Filtro por concessão oficial** — EGR, ECOSUL, CCR VIASUL, CSG, SACYR (cada uma com sua cor)
- **Filtro por ano de obra** — clica em cada ano na legenda para ligar/desligar
- **Municípios destacados** — ao selecionar bloco ou camada, os municípios cortados pelas rodovias acendem em amarelo no mapa
- **Lista de municípios** — painel lateral com todos os municípios afetados pela seleção atual
- **Basemap satélite** — Esri World Imagery + rótulos por padrão
- **Modo noturno** — toggle claro/escuro
- **Tabela retrátil** — clica no cabeçalho para expandir/recolher; interação bidirecional com o mapa
- **Download CSV** — exporta os dados visíveis na tabela
- **Exportar imagem** — captura o painel completo como PNG

---

## 🗂️ Estrutura de Arquivos

```
painel/
├── index.html                        # Painel principal (leve, ~50 KB)
├── README.md                         # Este arquivo
└── data/
    ├── municipios.geojson            # 497 municípios do RS (simplificado)
    ├── concedidas.geojson            # Rodovias concedidas oficiais
    ├── bloco1_dup.geojson            # Duplicações Bloco 1
    ├── bloco1_ers10.geojson          # ERS-010 (Bloco 1)
    ├── bloco2_dup.geojson            # Duplicações Bloco 2
    ├── bloco2_comp.geojson           # Composição Final Bloco 2 (referência)
    ├── bloco3_dup.geojson            # Duplicações Bloco 3 (CSG)
    ├── bloco4_dup.geojson            # Ampliações Bloco 4 (SACYR)
    └── municipios_por_camada.json    # Índice de municípios por camada
```

---

## 🔧 Como Atualizar os Dados

1. Abra o **Google Colab**
2. Rode `02_processar_dados.ipynb` para regrear os GeoJSONs a partir dos GeoPackages
3. Rode `03_painel.ipynb` para regrear o `index.html` e baixar o ZIP
4. Substitua os arquivos no repositório e faça novo commit

---

## 🛠️ Tecnologias

- [Leaflet.js 1.9.4](https://leafletjs.com/) — mapa interativo
- [Esri World Imagery](https://www.arcgis.com/) — basemap satélite
- [dom-to-image](https://github.com/tsayen/dom-to-image) — exportação PNG
- [GeoPandas](https://geopandas.org/) — processamento geoespacial
- [Google Colab](https://colab.research.google.com/) — ambiente de processamento

---

## 📋 Fonte dos Dados

- Geometrias das concessões: DAER/RS
- Dados de duplicações e ampliações: planilhas de obras dos blocos de concessão
- Municípios: IBGE 2020

---

*Desenvolvido para visualização e análise dos programas de duplicação e ampliação de rodovias estaduais do Rio Grande do Sul.*
