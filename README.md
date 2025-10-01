# Case Técnico iFood: Otimização de Campanhas de Ofertas

## Estrutura do Repositório

```
ifood-case/
├── data/
│   ├── raw/         # Dados originais em JSON
│   ├── bronze/      # Dados tipados em Parquet
│   ├── silver/      # Dados enriquecidos com regras de negócio
│   └── gold/        # Tabelas finais para modelagem (Feature Store, ABTs e Targets)
├── notebooks/
│   ├── 1_data_processing.ipynb
│   └── 2_modeling.ipynb
├── presentation/
│   └── Apresentacao_Executiva.pdf
├── requirements.txt # Dependências do projeto
└── README.md
```

## Como Executar o Projeto

### 1. Configuração do Ambiente
Clone o repositório e instale as dependências:
```bash
# Clone este repositório
git clone https://github.com/erasmo-aln/case-ifood.git
cd ifood-case

# Crie e ative um ambiente virtual
python -m venv .venv
source .venv/bin/activate

# Instale os pacotes necessários
pip install -r requirements.txt
```

### 2. Configuração do Caminho dos Dados
Ambos os notebooks utilizam uma variável `PATH_VOLUME` para definir o diretório raiz onde os dados serão lidos e salvos. **É necessário alterar esta variável** para o caminho correspondente na sua máquina.

**Exemplo (em `1_data_processing.ipynb` e `2_modeling.ipynb`):**
```python
PATH_VOLUME = "/caminho/para/sua/pasta/ifood-case/data"
```

### 3. Execução dos Notebooks
Os notebooks devem ser executados na seguinte ordem:

1.  **`notebooks/1_data_processing.ipynb`**: Responsável por todo o pipeline de dados, desde a leitura dos dados brutos até a criação das tabelas da camada Gold (utiliza Pyspark).
2.  **`notebooks/2_modeling.ipynb`**: Utiliza os dados da camada Gold para treinar os modelos, avaliar a performance e simular os cenários de negócio para análise de ROI.


## Conteúdo dos Notebooks

Ambos os notebooks foram documentados com células Markdown que explicam cada decisão técnica, as premissas adotadas, e uma discussão sobre as **limitações da abordagem e potenciais melhorias futuras** ao final. O objetivo é garantir que o raciocínio por trás do código esteja bem claro.
