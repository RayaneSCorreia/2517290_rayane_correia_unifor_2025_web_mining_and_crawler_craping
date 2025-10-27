# 📰 **Pipeline de Notícias e Cotações (Bronze → Silver → Gold)**  

*Extração, transformação e integração de dados financeiros e de notícias em camadas analíticas.*  

---

## 📁 **Notebooks**
| Notebook | Função |
|-------------|-----------|
| `extracao_noticias.ipynb` | Extração de notícias (Bronze) |
| `extracao_cotacao_dolar_fecha.ipynb` | Extração de cotações (Bronze) |
| `bronze-to-silver-noticias.ipynb` | Normalização de metadados (Silver) |
| `bronze-to-silver-conteudo-noticias.ipynb` | Limpeza e formatação de conteúdo (Silver) |
| `bronze-to-silver-cotacao.ipynb` | Normalização de cotações (Silver) |

---

## 🎨 **Camadas de Dados**
| Camada | Descrição |
|:------:|-----------|
| 🟤 **Bronze** | Dados crus coletados diretamente das fontes (JSON/HTML). |
| ⚪ **Silver** | Dados tratados e normalizados. |
| 🟡 **Gold** | Dataset final integrado (ex.: notícias + cotações). |

---

## 🧮 **Requisitos**
```txt
# Python 3.11
beautifulsoup4==4.12.3
numpy==1.26.4
pandas==2.2.2
requests==2.32.3
selenium==4.23.1
webdriver-manager==4.0.2
```

---

## 🚀 **Como Executar**
```bash
python -m venv .venv
source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt
```

---

## 🧭 **Ordem Recomendada**
1. `extracao_noticias.ipynb`  
2. `extracao_cotacao_dolar_fecha.ipynb`  
3. `bronze-to-silver-noticias.ipynb`  
4. `bronze-to-silver-conteudo-noticias.ipynb`  
5. `bronze-to-silver-cotacao.ipynb`  
6. Criação do dataset Gold (join de notícias + cotações).

---


## 🧱 **Visualização do Fluxo de Dados**
```text
[🔹 Extração BRONZE] --> [ 🔹 Limpeza SILVER] --> [ 🔹 Integração GOLD]
          |                       |                        |
     JSON / HTML             DataFrames              Parquet final
```
---

💡 *Este repositório segue a arquitetura de camadas típica de pipelines de dados modernos (inspirada no conceito Medallion do Databricks).*  


👩‍💻 Autora

Rayane Correia — Analytics Engineer | Pós-graduação em Engenharia de Dados – UNIFOR