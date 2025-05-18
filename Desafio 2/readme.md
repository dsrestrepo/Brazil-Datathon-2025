# Desafio 2: Prevenção de Surtos de Dengue na Amazônia

## Português

### Motivação  
A dengue é uma doença endêmica na região Amazônica, cujos surtos variam fortemente com as condições climáticas e ambientais. Desenvolver sistemas de alerta precoce e ferramentas de análise capazes de antecipar áreas de risco contribui para a alocação eficiente de recursos, redução de custos e, sobretudo, para salvar vidas.

**Objetivo**  
Criar modelos preditivos e dashboards interativos que integrem séries temporais de casos de dengue, variáveis meteorológicas e características geoespaciais, de modo a oferecer aos gestores de saúde públicos indicadores de risco em tempo real e recomendações de intervenção.

**Perguntas Motivacionais**  
- Quais municípios ou bairros apresentam maior probabilidade de surto nas próximas semanas, dado o comportamento recente de chuva, temperatura e umidade?  
- Como incorporar índices de vegetação ou uso do solo melhora a precisão das previsões?  
- Onde concentrar ações de controle vetorial (fumacê, mutirões de limpeza) para obter o maior impacto preventivo?  
- É possível construir um painel de monitoramento em tempo real que combine previsão de risco e alertas georreferenciados?

### Dados principais  
- **SINAN (casos semanais de dengue em Manaus)**  
- **Meteostat (temperatura, precipitação e umidade horárias/diárias)**  
- **Shapefiles (rodovias, rios e divisões administrativas)**  

💾 **Links de download**  
- Dados do Desafio 2: https://drive.google.com/drive/folders/10vUqT7sycYhkxe_h-BaRYbxq4Ga_WVWg?usp=sharing  
- Shapefiles (todas as camadas): https://drive.google.com/drive/folders/1Ohl8Yk49cSWnIG94WkVanQZ4meRr-WUB?usp=sharing  

### Notebooks  
- **Colab:** https://colab.research.google.com/drive/14sWxhn8x3_X6PGAcLBvAT5K-peR1DPVf?usp=sharing  
- **Local:** `Desafio 2/Desafio 2.ipynb`

### Instruções (Colab)  
1. Abra o notebook no Colab.  
2. Monte seu Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
    ```
3. Defina os caminhos:
   ```python
    base   = '/content/drive/My Drive/amazonia-datathon-2025/Desafio 2'
    data   = f'{base}/Dataset_Desafio_2'
    shapes = '/content/drive/My Drive/amazonia-datathon-2025/Shapefiles'
   ```
4. Carregue e explore os dados:
    ```python
    import pandas as pd
    import geopandas as gpd
    
    # Carregar dados
    df = pd.read_csv(f'{data}/dados.csv')
    gdf = gpd.read_file(shapes + '/norte-latest-free.shp.zip', layer='gis_osm_roads_free_1')
    
    # Explorar dados
    print(df.head())
    print(gdf.head())
    ```
    
5. Propostas de análise (não exaustivas):

- Treinar modelos para previsão de casos nas próximas 1–4 semanas.

- Aplicar explicações SHAP para entender quais variáveis climáticas mais influenciam o risco.

- Integrar índices de vegetação via satélite para refinar mapas de vulnerabilidade.

- Construir dashboard em Plotly Dash ou Streamlit para visualização georreferenciada de alertas.

### Exemplos motivacionais

- [A multimodal framework for extraction and fusion of satellite images and public health data](https://www.nature.com/articles/s41597-024-03366-1)  
- [Forecasting dengue across Brazil with LSTM neural networks and SHAP-driven lagged climate and spatial effects](https://link.springer.com/article/10.1186/s12889-025-22106-7)

---
## English

# Challenge 2: Dengue Outbreak Prevention in the Amazon

### Motivation
Dengue is an endemic disease in the Amazon region, with outbreaks strongly influenced by climatic and environmental conditions. Developing early warning systems and analytical tools capable of anticipating risk areas contributes to efficient resource allocation, cost reduction, and, most importantly, saving lives.

**Objective**
Create predictive models and interactive dashboards that integrate time series of dengue cases, meteorological variables, and geospatial characteristics, providing public health managers with real-time risk indicators and intervention recommendations.

**Motivational Questions**
- Which municipalities or neighborhoods are at the highest risk of an outbreak in the coming weeks, given recent rainfall, temperature, and humidity patterns?
- How does incorporating vegetation indices or land use improve prediction accuracy?
- Where should vector control actions (fogging, cleanup campaigns) be concentrated for maximum preventive impact?
- Is it possible to build a real-time monitoring dashboard that combines risk forecasting and georeferenced alerts?

### Main Datasets
- **SINAN (weekly dengue cases in Manaus)**
- **Meteostat (hourly/daily temperature, precipitation, and humidity)**
- **Shapefiles (roads, rivers, and administrative divisions)**

💾 **Download Links**

- Challenge 2 data: https://drive.google.com/drive/folders/10vUqT7sycYhkxe_h-BaRYbxq4Ga_WVWg?usp=sharing
- Shapefiles (all layers): https://drive.google.com/drive/folders/1Ohl8Yk49cSWnIG94WkVanQZ4meRr-WUB?usp=sharing

### Notebooks
- **Colab:** https://colab.research.google.com/drive/14sWxhn8x3_X6PGAcLBvAT5K-peR1DPVf?usp=sharing
- **Local:** `Desafio 2/Desafio 2.ipynb`

### Instructions (Colab)
1. Open the notebook in Colab.
2. Mount your Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
    ```
3. Set the paths:
    ```python
     base   = '/content/drive/My Drive/amazonia-datathon-2025/Desafio 2'
     data   = f'{base}/Dataset_Desafio_2'
     shapes = '/content/drive/My Drive/amazonia-datathon-2025/Shapefiles'
    ```
4. Load and explore data:
    ```python
    import pandas as pd
    import geopandas as gpd

    # Load data
    df = pd.read_csv(f'{data}/dados.csv')
    gdf = gpd.read_file(shapes + '/norte-latest-free.shp.zip', layer='gis_osm_roads_free_1')

    # Explore data
    print(df.head())
    print(gdf.head())
    ```
5. Analysis proposals (non-exhaustive):

- Train models to predict cases in the next 1–4 weeks.
- Apply SHAP explanations to understand which climatic variables most influence risk.
- Integrate satellite vegetation indices to refine vulnerability maps.
- Build a dashboard in Plotly Dash or Streamlit for georeferenced alert visualization.

### Motivational Examples

- [A multimodal framework for extraction and fusion of satellite images and public health data](https://www.nature.com/articles/s41597-024-03366-1)
- [Forecasting dengue across Brazil with LSTM neural networks and SHAP-driven lagged climate and spatial effects](https://link.springer.com/article/10.1186/s12889-025-22106-7)
