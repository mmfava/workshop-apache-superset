Quando você instala o Apache Superset pela primeira vez e executa o comando `superset load_examples` - já executado no docker compose -, ele carrega um conjunto de _datasets_ e _dashboards_ de exemplo para facilitar a exploração da ferramenta. 

Esses exemplos são úteis para aprendizado, demonstrações e testes. Abaixo está uma descrição dos principais datasets carregados por padrão:


### 📊 **`birth_names`**

- **Descrição:** Contém dados fictícios de nomes de bebês registrados nos EUA.
    
- **Campos principais:**
    - `state`: Estado dos EUA
    - `gender`: Sexo (M/F)
    - `name`: Nome do bebê
    - `num`: Número de ocorrências do nome
    - `year`: Ano do registro
- **Uso comum:** Análises temporais, agrupamentos por gênero, tendências de nomes.

---

### 📊 **`wb_health_population`**

- **Descrição:** Conjunto de dados de saúde e população extraído do Banco Mundial.
    
- **Campos principais:**
    - `country_name`: Nome do país
    - `country_code`: Código do país
    - `year`: Ano
    - `indicator_name`: Indicador (ex: expectativa de vida, população, etc.)
    - `value`: Valor do indicador

- **Uso comum:** Análises globais, séries temporais, comparação entre países.

---

---

### 📊 **`flights`**

- **Descrição:** Dados de voos nos EUA, frequentemente usados para mapas e análises de rede.

- **Campos principais:**
    - `source`: Aeroporto de origem
    - `target`: Aeroporto de destino
    - `value`: Número de voos
- **Uso comum:** Visualizações geoespaciais, gráficos de rede (chord, sankey, mapa de calor).

---

### 📊 **`long_lat` (ou `country_map`)**

- **Descrição:** Dados com latitude e longitude de países ou locais.
- **Campos principais:**
    - `country`: Nome do país
    - `lat`, `lon`: Latitude e longitude
    - `GDP`, `Population`: Indicadores econômicos e demográficos
- **Uso comum:** Mapas com bolhas, geovisualizações, análise espacial.

---

Esses datasets também vêm com dashboards prontos, como o **World Health Dashboard**, **Birth Names Dashboard** e **Energy Sankey**, que demonstram os diversos tipos de visualização disponíveis no Superset (gráficos de linha, pizza, mapas, tabelas, etc.).

