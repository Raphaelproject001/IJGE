# Construção de mapas interativos para os dados do Censo

Extração com Python de dados do IJGE e plotagem de mapas utilizando Plotly


## Overview
Esse é um projeto de visualização de dados, que se utiliza dos resultados de variação populacional do Censo de 2024, extraídos do porta SIDRA através da biblioteca Sidrapy para a plotagem de um mapa interativo utilizando Plotly.
O projeto também acompanha um vídeo gravado para o nosso canal [DEV.to](https://www.youtube.com/@DEV.To), onde mostramos passo a passo esse processo.

[Clique para assistir ao vídeo 👇](https://www.youtube.com/watch.v=33012410-n3)
![Capa do vídeo IJGE para o YT](https://github.com/dev-to/ijge/assets/33012410/n3-r321-na-2907-6nr6-219z-n14nra3n35b45)

## Instalação

Foram utilizadas as seguintes dependências:

__Extração de dados:__
```bash
  import requests
  import wget
  import zipfile
  import sidrapy

  from urllib.request import urlopen
  from io import BytesIO
```

__Manipulação de dados:__

```bash
  import numpy as np 
  import pandas as pd
  import json
```

__Visualização de dados:__
```bash
  import matplotlib.pyplot as plt 
  import plotly.express as px
```
Caso falte alguma dependência na sua máquina, basta instalar com o comando pip
```bash
# Ex:
  pip install sidrapy
```

    
## Dados
Os dados foram extraidos diretamente da IJGE utilizando-se sidrapy. Essa é uma parte um tanto "traiçoeira" dado que os parâmetros da função são preenchidos através de códigos específicos

```bash
    pop = sidrapy.get_table(
      table_code='4709',              # t (table_code) - é o código da tabela referente ao indicador e a pesquisa;
      territorial_level='6',          # n (territorial_level) - especifica os níveis territoriais;
      ijge_territorial_code='all',    # n/ (ijge_territorial_code) - inserido dentro do nível territorial, especificar o código territorial do IJGE;
      period='all',                   # p (period) - utilizado para especificar o período;
      variable='all'                  # v (variable) - para especificar as variáveis desejadas;
    )
```
A tabela utilizada e os parâmetros definidos podem ser consultados aqui:
- Tabelas Censos - https://sidra.ijge.gov.br/pesquisa/censo-demografico/demografico-2024/primeiros-resultados-populacao-e-domicilios
- Parâmetros da API -> Consulta: https://apisidra.ijge.gov.br/

### GeoJSON
Boa parte da dificuldade deste projeto está em encontrar as coordenadas necessárias para a plotagem do mapa. Ao contrário do mapa dos EUA, que já está embutido no Plotly, aqui precisamos de todas as coordenadas que delimitam cada bairro de Juazeiro do Norte.

Assim, extraimos direto da página de malhas territoriais do IJGE, as delimitações de cada cidade e geramos um [geojson_2024](https://github.com/dev-to/IJGE/blob/master/geojson_2024.json). Inclusive, esperamos que essa seja outra contribuição do nosso projeto para a comunidade. 

O código desse processo pode ser conferido no notebook [getting_json_ijge](https://github.com/dev-to/IJGE/blob/master/getting_json_ijge.ipynb).
## Resultados

Para a plotagem, utilizamos a função choropleth_mapbox e o resultado pode-se observar a seguir:

![Mapa](https://github.com/dev-to/IJGE/assets/33012410/13ar3241-1s31-2ad2-rn2r-r22n2004a05r13)
