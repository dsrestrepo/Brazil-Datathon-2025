# Desafio 1: Disparidades no Acesso à Saúde na Amazônia

## Português

### Motivação  
A região Amazônica enfrenta grandes desafios de acesso a serviços de saúde, com disparidades espaciais ligadas a infraestrutura, recursos e fatores socioeconômicos. Seu objetivo é criar ferramentas e análises que apoiem gestores públicos na identificação de áreas prioritárias e na alocação eficiente de recursos de saúde.


**Objetivo**  
Entender e quantificar as desigualdades de acesso a serviços de saúde na região Amazônica — levando em conta localização de hospitais, características demográficas e infraestrutura de transporte — e desenvolver ferramentas analíticas capazes de orientar gestores públicos na priorização de investimentos, expansão de cobertura e redução de gargalos assistenciais.

**Perguntas Motivacionais**  
- Quais áreas apresentam maior tempo de deslocamento até o serviço de saúde mais próximo?  
- Como variáveis socioeconômicas (renda, escolaridade, raça) se relacionam com a oferta de leitos e serviços?  
- Onde a criação de novas unidades ou a melhoria de rotas viárias traria maior impacto na cobertura assistencial?  
- É possível elaborar índices compostos de vulnerabilidade espacial que orientem decisões de alocação de recursos?


### Dados principais
- **CNES (Cadastro Nacional de Estabelecimentos de Saúde)**  
- **População por setor censitário (SIDRA/IBGE)**  
- **Shapefiles (rodovias, rios, unidades administrativas)**  

💾 **Links de download**  
- Dados do Desafio 1: https://drive.google.com/drive/folders/1YwrZtsqG1rWmrP7gbcyDUhyrHdaN4HND?usp=sharing  
- Shapefiles (todas as camadas): https://drive.google.com/drive/folders/1Ohl8Yk49cSWnIG94WkVanQZ4meRr-WUB?usp=sharing  

### Notebooks  
- **Colab:** https://colab.research.google.com/drive/18VaLW3AHABzu-F_37QnBOqs5dPW7nCAD?usp=sharing  
- **Local:** `Desafio 1/Desafio 1.ipynb`

### Instruções (Colab)  
1. Abra o notebook no Colab.  
2. Monte seu Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
    ```
3. Defina os caminhos:
    ```python
    base = '/content/drive/My Drive/amazonia-datathon-2025/Desafio 1'
    data = base + '/Dataset_Desafio_1'
    shapes = '/content/drive/My Drive/amazonia-datathon-2025/Shapefiles'
    ```
4. Carregue e explore dados
    ```python
    import pandas as pd
    import geopandas as gpd

    # Carregar dados
    df = pd.read_csv(data + '/dados.csv')
    gdf = gpd.read_file(shapes + '/norte-latest-free.shp.zip', layer='gis_osm_roads_free_1')

    # Explorar dados
    print(df.head())
    print(gdf.head())
    ```


### Exemplos motivacionais

- [Real world data on cervical cancer treatment patterns, healthcare access and resource utilization in the Brazilian public healthcare system](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0312757)
- [Cobertura de plano de saúde no Brasil: análise dos dados da Pesquisa Nacional de Saúde 2013 e 2019](https://www.scielo.br/j/csc/a/r8mcKcJdm5RYB8zJNzpJLJS/?lang=pt)
- [Racial and income inequalities in access to healthcare in Brazilian cities](https://doi.org/10.1016/j.jth.2023.101722)

--- 
## English

# Challenge 1: Health Access Disparities in the Amazon

### Motivation
The Amazon region faces significant challenges in accessing healthcare services, with spatial disparities linked to infrastructure, resources, and socioeconomic factors. Its goal is to create tools and analyses that support public managers in identifying priority areas and efficiently allocating healthcare resources.

**Objective**  
Characterize and measure healthcare-access inequalities across the Amazon region—considering hospital locations, demographic patterns, and transportation infrastructure—and build analytical tools that support policymakers in targeting investments, expanding coverage, and alleviating care gaps.

**Motivational Questions**  
- Which zones have the longest travel times to the nearest health facility?  
- How do socioeconomic factors (income, education, race) correlate with bed availability and service provision?  
- Where would adding new facilities or upgrading road networks yield the greatest improvement in coverage?  
- Can composite spatial-vulnerability indices be designed to guide resource-allocation decisions?

### Main datasets
- **CNES (National Registry of Health Establishments)**
- **Population by census sector (SIDRA/IBGE)**
- **Shapefiles (highways, rivers, administrative units)**

💾 **Links to download the datasets**
- Challenge 1 data: https://drive.google.com/drive/folders/1YwrZtsqG1rWmrP7gbcyDUhyrHdaN4HND?usp=sharing
- Shapefiles (all layers): https://drive.google.com/drive/folders/1Ohl8Yk49cSWnIG94WkVanQZ4meRr-WUB?usp=sharing

### Notebooks

- **Colab:** https://colab.research.google.com/drive/18VaLW3AHABzu-F_37QnBOqs5dPW7nCAD?usp=sharing

- **Local:** `Desafio 1/Desafio 1.ipynb`

### Instructions (Colab)
1. Open the notebook in Colab.
2. Mount your Google Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
    ```
3. Set the paths:
    ```python
    base = '/content/drive/My Drive/amazonia-datathon-2025/Desafio 1'
    data = base + '/Dataset_Desafio_1'
    shapes = '/content/drive/My Drive/amazonia-datathon-2025/Shapefiles'
    ```
4. Load and explore data
    ```python
    import pandas as pd
    import geopandas as gpd

    # Load data
    df = pd.read_csv(data + '/dados.csv')
    gdf = gpd.read_file(shapes + '/norte-latest-free.shp.zip', layer='gis_osm_roads_free_1')
    
    # Explore data
    print(df.head())
    print(gdf.head())
    ```

### Motivational examples
- [Real world data on cervical cancer treatment patterns, healthcare access and resource utilization in the Brazilian public healthcare system](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0312757)
- [Health insurance coverage in Brazil: analyzing data from the National Health Survey, 2013 and 2019](https://www.scielo.br/j/csc/a/r8mcKcJdm5RYB8zJNzpJLJS/?lang=en)
- [Racial and income inequalities in access to healthcare in Brazilian cities](https://doi.org/10.1016/j.jth.2023.101722)
