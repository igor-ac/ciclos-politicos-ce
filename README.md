# Ciclos Políticos do Ceará (1994–2024)

**Autor:** Igor Cavalcante  
**Curso:** MBA em Jornalismo de Dados — IDP  
**Projeto:** Trabalho de Conclusão de Curso  
**Tema:** Força e reconfiguração dos grupos políticos cearenses nas urnas  

---

## Descrição

O projeto **“Ciclos Políticos do Ceará”** analisa três décadas de eleições — de 1994 a 2024 — para identificar **como os grupos políticos que dominaram o Estado se formaram, se transformaram e se mantêm no poder**.  

A partir de dados oficiais do **TSE (Tribunal Superior Eleitoral)**, o estudo busca compreender:
- O comportamento eleitoral das principais siglas partidárias no Ceará;  
- As relações entre o cenário local e as tendências nacionais;  
- A força dos grupos políticos tradicionais.  

---

## Estrutura do Projeto

```
ciclos-politicos-ce/
│
│   dados_nacionais.csv¹
│   lista-zonas-municipios-24.csv
│   README.md
│
├── br_dados_brutos/²
│   ├── gerais/²
│   └── municipais/²
│
├───br_dados_processados/
│       coeficientes_deputados_BR_CE.csv
│       coeficientes_dep_estadual_BR_CE.csv
│       coeficientes_dep_federal_BR_CE.csv
│       coeficientes_prefeitos_BR_CE.csv
│       coeficiente_dep.csv
│       coeficiente_prefeitos.csv
│       dados_deputados_agrupados.csv
│       dep_eleitos_agrupados.csv
│       df_deputados_eleitos.csv
│       df_deputados_eleitos_ce.csv
│       df_deputados_estaduais_eleitos_ce.csv
│       df_deputados_federais_eleitos_ce.csv
│       df_deputados_FEDERAL_lulismo_bolsonarismo.csv
│       df_deputados_lulismo_bolsonarismo.csv
│       df_deputado_ESTADUAL_lulismo_bolsonarismo.csv
│       df_prefeitos_lulismo_bolsonarismo.csv
│       partidos_eleitos_mun_ce.csv
│       prefeitos_eleitos.csv
│       prefeitos_eleitos_ce.csv
│       selecionados_deputados_estadual_25_CE.csv
│       selecionados_deputados_estadual_5_CE.csv
│       selecionados_deputados_federal_25_CE.csv
│       selecionados_deputados_federal_5_CE.csv
│       selecionados_prefeitos_25_CE.csv
│       selecionados_prefeitos_5_CE.csv
│       votos_partido_deputados_municipio_ce.csv
│
└───notebooks/
        1. Processamento.ipynb
        2. Análise.ipynb
        3. Visualização.ipynb
```
¹ Por conta do tamanho, o arquivo já processado pode ser baixado [neste link](https://drive.google.com/file/d/1PT-RaOm3iwkSIWlOJDO9whCvQLrQMPQ4/view?usp=drive_link).

² Tamnbém por conta do tamanho dos arquivos originais, as pastas precisam ser preenchidas com os arquivos disponíveis nos Dados Abertos do TSE para executar o notebook ´1. Processamento.ipynb´.

## Fonte de dados

Para reproduzir as análises, é necessário baixar os arquivos originais disponibilizados pelo TSE.
Acesse o repositório de Dados Abertos do TSE, selecione o conjunto “Resultados” e faça o download do arquivo:

“Votação nominal por município e zona” para cada um dos anos abaixo.

Em seguida, salve nas pastas específicas dentro de ´br_dados_brutos´

**Eleições Gerais**
| Ano                   | Link direto                                                                                                |
| --------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Eleições 1994** | [dadosabertos.tse.jus.br/dataset/resultados-1994](https://dadosabertos.tse.jus.br/dataset/resultados-1994) |
| **Eleições 1998** | [dadosabertos.tse.jus.br/dataset/resultados-1998](https://dadosabertos.tse.jus.br/dataset/resultados-1998) |
| **Eleições 2002** | [dadosabertos.tse.jus.br/dataset/resultados-2002](https://dadosabertos.tse.jus.br/dataset/resultados-2002) |
| **Eleições 2006** | [dadosabertos.tse.jus.br/dataset/resultados-2006](https://dadosabertos.tse.jus.br/dataset/resultados-2006) |
| **Eleições 2010** | [dadosabertos.tse.jus.br/dataset/resultados-2010](https://dadosabertos.tse.jus.br/dataset/resultados-2010) |
| **Eleições 2014** | [dadosabertos.tse.jus.br/dataset/resultados-2014](https://dadosabertos.tse.jus.br/dataset/resultados-2014) |
| **Eleições 2018** | [dadosabertos.tse.jus.br/dataset/resultados-2018](https://dadosabertos.tse.jus.br/dataset/resultados-2018) |
| **Eleições 2022** | [dadosabertos.tse.jus.br/dataset/resultados-2022](https://dadosabertos.tse.jus.br/dataset/resultados-2022) |

**Eleições Municipais**
| Ano               | Link direto                                                                                                |
| ----------------- | ---------------------------------------------------------------------------------------------------------- |
| **Eleições 2000** | [dadosabertos.tse.jus.br/dataset/resultados-2000](https://dadosabertos.tse.jus.br/dataset/resultados-2000) |
| **Eleições 2004** | [dadosabertos.tse.jus.br/dataset/resultados-2004](https://dadosabertos.tse.jus.br/dataset/resultados-2004) |
| **Eleições 2008** | [dadosabertos.tse.jus.br/dataset/resultados-2008](https://dadosabertos.tse.jus.br/dataset/resultados-2008) |
| **Eleições 2012** | [dadosabertos.tse.jus.br/dataset/resultados-2012](https://dadosabertos.tse.jus.br/dataset/resultados-2012) |
| **Eleições 2016** | [dadosabertos.tse.jus.br/dataset/resultados-2016](https://dadosabertos.tse.jus.br/dataset/resultados-2016) |
| **Eleições 2020** | [dadosabertos.tse.jus.br/dataset/resultados-2020](https://dadosabertos.tse.jus.br/dataset/resultados-2020) |
| **Eleições 2024** | [dadosabertos.tse.jus.br/dataset/resultados-2024](https://dadosabertos.tse.jus.br/dataset/resultados-2024) |

---

## Etapas do Projeto

1. **Processamento de dados brutos**  
   - Leitura de arquivos do TSE (1994–2024) e padronização de colunas.  
   - Unificação de siglas partidárias considerando incorporações.  
   - Geração de bases intermediárias por cargo e por recorte geográfico.

2. **Cálculo de indicadores**
   - Coeficientes eleitorais para cada sigla (Ceará e Brasil).  
   - Identificação de partidos dominantes e flutuações no desempenho.  

3. **Seleção e relevância partidária**
   - Manutenção apenas das legendas com coeficiente ≥ 25 em algum ciclo.  
   - Preenchimento de anos ausentes com 0 para visualizações temporais.  

4. **Análise e visualização**
   - Construção de séries históricas no **Flourish Studio**.  
   - Comparativos entre ciclos e entre cargos (prefeitos, deputados estaduais e federais).  

---

## Principais Arquivos

| Categoria | Nome do Arquivo | Descrição |
|------------|-----------------|------------|
| 📊 Base geral | `dados_nacionais.csv` | Síntese dos resultados nacionais e estaduais |
| 🏛️ Deputados | `coeficientes_dep_estadual_BR_CE.csv` / `coeficientes_dep_federal_BR_CE.csv` | Coeficientes eleitorais por partido e cargo |
| 🏙️ Prefeitos | `coeficientes_prefeitos_BR_CE.csv` | Desempenho municipal das siglas |
| 📈 Séries filtradas | `selecionados_*_25_CE.csv` e `selecionados_*_5_CE.csv` | Recortes com coeficientes acima de 25% e 5% |
| 📘 Notebooks | `1. Processamento.ipynb` / `2. Análise.ipynb` / `3. Visualização.ipynb` | Etapas completas do pipeline de dados e análises |

---

## Visualizações

As visualizações foram geradas no **Flourish Studio**, com foco em:
- Evolução das forças partidárias no Ceará;  
- Comparativos entre ciclos eleitorais (1994–2024);  
- Distribuição municipal e concentração de poder político.  

### **Acesso direto ao Flourish**

#### **Comparativo do desempenho (%) do Ceará em relação à média nacional**

* [CE x BR — Desempenho Estadual](https://public.flourish.studio/visualisation/26014621/)
* [CE x BR — Desempenho Federal](https://public.flourish.studio/visualisation/25976830/)
* [CE x BR — Desempenho Prefeitos](https://public.flourish.studio/visualisation/26014663/)

#### **Comparativo do desempenho (%) dos partidos com melhores resultados no Ceará (≥ 30%)**

* [Prefeitos — Siglas dominantes no Ceará](https://public.flourish.studio/visualisation/26061550/)
* [Deputados Estaduais — Siglas dominantes no Ceará](https://public.flourish.studio/visualisation/26093985/)
* [Deputados Federais — Siglas dominantes no Ceará](https://public.flourish.studio/visualisation/26093848/)

#### **Efeitos da polarização no desempenho (%) das siglas de Lula e Bolsonaro no Ceará**

* [Polarização — Prefeitos](https://public.flourish.studio/visualisation/26111072/)
* [Polarização — Deputados](https://public.flourish.studio/visualisation/26111197/)

#### **Quantitativo absoluto de prefeitos e deputados eleitos no Ceará**

* [Prefeitos eleitos no Ceará](https://public.flourish.studio/visualisation/25982911/)
* [Deputados eleitos no Ceará](https://public.flourish.studio/visualisation/26037615/)

---

## Tecnologias Utilizadas

- **Python 3.11**  
  - pandas   
  - pathlib 
  - os
  - re
- **Flourish Studio** (visualização interativa)  
- **VS Code** (ambiente de desenvolvimento)

---

## Licença e Uso

Este projeto é de uso **acadêmico e jornalístico**.  
Reprodução de partes do código ou dos dados é permitida mediante citação:

> *CAVALCANTE, Victor Igor A.. O que três décadas de urnas revelam sobre a força e a renovação dos grupos políticos que dominam o Ceará. Medium, 2025. Disponível em: https://medium.com/@victorigor.ac.*

---

## Contato

**Igor Cavalcante**  
Jornalista.
📧 victorigor.ac@gmail.com  
🔗 [linkedin.com/in/igor-cavalcante](linkedin.com/in/igor-cavalcante)
