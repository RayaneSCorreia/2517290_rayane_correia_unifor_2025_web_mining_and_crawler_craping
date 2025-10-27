# Pipeline de Notícias e Cotações (Bronze → Silver → Gold)
Este repositório contém notebooks para **extração de notícias e cotações**, normalização e gravação em **Parquet** seguindo as camadas **Bronze → Silver → Gold**.

## Notebooks

- **bronze-to-silver-conteudo-noticias.ipynb** — Transformação do conteúdo das notícias de Bronze → Silver (normalização/limpeza).
  - Observação: _<h2> Tabela ja particionada pela mesma data da principal para facilitar joins e dificultar full load na camada ouro_
- **bronze-to-silver-noticias.ipynb** — Transformação de metadados de notícias de Bronze → Silver.
  - Observação: _<H2> Validação de conteudo_
- **bronze-to-silver-cotacao.ipynb** — Transformação de cotações de Bronze → Silver.
  - Observação: _<H2> Validando diferencas entre o que foi lindo e o que foi escrito:_
- **extracao_cotacao_dolar_fecha.ipynb** — Extração de cotações cambiais e persistência Bronze.
- **extracao_noticias.ipynb** — Extração de notícias (scraping/API) e persistência Bronze.
  - Observação: _<H2> BASE DE DADOS SOBRE A PESQUISA EXTRAIDA PARA INFORMACOES RESUMIDAS DA SEGUNDA BASE - CHAVE - link_

## Convenções de dados
- **Bronze**: dados crus como coletados (JSON/HTML → Parquet).
- **Silver**: dados limpos e normalizados (datas normalizadas, colunas padronizadas).
- **Gold**: dataset final integrado (ex.: notícias + cotações) para consumo analítico.

## Ordem sugerida de execução
1. **`extracao_noticias.ipynb`** → coleta de notícias (Bronze)
2. **`extracao_cotacao_dolar_fecha.ipynb`** → coleta de cotações (Bronze)
3. **`bronze-to-silver-noticias.ipynb`** → normalização das notícias (Silver)
4. **`bronze-to-silver-conteudo-noticias.ipynb`** → normalização do conteúdo (Silver)
5. **`bronze-to-silver-cotacao.ipynb`** → normalização das cotações (Silver)
6. **Gold (dataset final)** → criação do dataset integrado

## Requisitos e Setup
## Requisitos
- Python **3.11.8** (recomendado)
### Dependências (pip)
```txt
beautifulsoup4
numpy
pandas
requests
selenium
webdriver-manager
```

