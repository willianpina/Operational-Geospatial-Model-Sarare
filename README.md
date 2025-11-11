## 🛰️ **Operational Geospatial - Model-Sarare**

**Modelo Geoespacial Integrado para Identificação de Áreas de Garimpo Ilegal na Terra Indígena Sararé (MT)**

---

### 📖 **Descrição do Projeto**

Este projeto implementa um **modelo geoespacial integrado** para **identificar e priorizar áreas de interesse** associadas à **atividade garimpeira ilegal** dentro da **Terra Indígena Sararé**, no estado de Mato Grosso.
O fluxo combina **sensoriamento remoto, análise de relevo, índices espectrais (NDVI/NDWI)** e **fatores logísticos de acesso**, produzindo mapas temáticos e estatísticas de risco espacial.

O modelo foi desenvolvido em **Python** com apoio das bibliotecas `rasterio`, `geopandas`, `numpy` e `matplotlib`, visando uso **operacional** por equipes de inteligência e fiscalização ambiental.

---

### 🧭 **Metodologia Integrada**

A delimitação das **Áreas de Interesse** é resultado da sobreposição ponderada de cinco camadas derivadas das etapas anteriores:

1. **Relevo Favorável:**
   Áreas com **declividade ≤ 6°**, derivadas do **Copernicus DEM**, indicando terrenos planos ou suavemente ondulados adequados ao uso de maquinário pesado.

2. **Cobertura Vegetal Degradada:**
   Regiões com **NDVI < 0.6**, representando clareiras, solo exposto ou áreas desmatadas — potenciais locais de intervenção recente.

3. **Proximidade de Recursos Hídricos:**
   Zonas com **NDWI > 0.2**, indicando presença de umidade e corpos d’água usados na lavagem de minério e abastecimento.

4. **Acessibilidade Logística:**
   Buffer de **até 800 m** em torno de ramais e rodovias mapeados, indicando **facilidade de transporte e suporte operacional** ao garimpo.

5. **Interseção de Fatores:**
   A combinação simultânea desses critérios define as **Áreas de Alta Prioridade**, com maior probabilidade de ocorrência de estruturas clandestinas.

---

### 🗺️ **Resultados Principais**

**Área Total Analisada:** ~1424 km²

| Prioridade | Nº de Pixels | Área (km²) | Percentual |
| ---------- | ------------ | ---------- | ---------- |
| 0 - Nenhum | 749,671      | 650.81     | 45.7%      |
| 1 - Baixa  | 619,720      | 537.99     | 37.8%      |
| 2 - Média  | 269,403      | 233.87     | 16.4%      |
| 3 - Alta   | 1,456        | 1.26       | 0.1%       |

As **áreas de alta prioridade (classe 3)** indicam regiões planas, degradadas e próximas a vias e drenagens — condições logísticas típicas de operação de maquinário pesado.

---

### 🧩 **Estrutura do Projeto**

```
GarimpoDetector-Sarare/
│
├── Analise_SARARE/
│   ├── NDVI_Sarare.tif
│   ├── NDWI_Sarare.tif
│   ├── DEM_Sarare.tif
│   ├── Slope_Sarare.tif
│   ├── Mapa_Areas_Interesse_Sarare.tif
│   ├── Mapa_Areas_Interesse_Sarare.png
│
├── RODOVIAS_RAMAIS/
│   └── rodovias_ramais_TI_Sarare.gpkg
│
├── TI_BRASIL/
│   └── tis_poligonaisPolygon.shp
│
├── notebooks/
│    └── Analise_Terreno_TISAR.ipynb
│
└── README.md
```

---

### ⚙️ **Dependências Principais**

O projeto requer Python ≥ 3.10 e os seguintes pacotes:

```bash
pip install geopandas rasterio matplotlib numpy shapely scikit-learn
```

---

### 🚀 **Execução**

1. Clone este repositório:

   ```bash
   git clone https://github.com/seuusuario/GarimpoDetector-Sarare.git
   ```
2. Coloque as imagens e shapefiles nos diretórios correspondentes.
3. Execute o notebook:

   * `Analise_Terreno_TISAR.ipynb`

   
4. Os resultados (GeoTIFF e PNG) serão gerados automaticamente na pasta `Analise_SARARE/`.

---

### 📊 **Interpretação Operacional**

O modelo foi calibrado com base em parâmetros físicos e espectrais derivados de sensores ópticos e topográficos.
Sua aplicação operacional visa apoiar **planejamento de missões de fiscalização**, permitindo **priorizar áreas críticas** para atuação de campo, drones ou aquisição de imagens de alta resolução.

---

### 🛡️ **Impacto da Operação**

Durante a operação associada a este estudo, o **IBAMA**, com **apoio direto e indireto de diversos órgãos federais e estaduais**, **neutralizou 160 retroescavadeiras**, resultando em **prejuízo milionário aos infratores** e contribuindo significativamente para o **enfraquecimento das estruturas de garimpo ilegal na TI Sararé**.

---

### 🧾 **Licença**

Este repositório é distribuído sob a licença **MIT**, permitindo uso acadêmico, operacional e extensão em outros estudos ambientais, mediante citação da fonte original.

---

### 🧑‍💻 **Autor**

**Willian Pina Botelho**
Coordenador de Apoio às Operações (COAP) – CENSIPAM
*Mestrando em Ciência de Dados (MSDS)*
📍 *Brasil*
