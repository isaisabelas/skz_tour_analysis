# 🎤 Stray Kids Tour Analysis

Um projeto completo de engenharia de dados para análise das turnês do Stray Kids, desde a coleta até visualizações interativas.

## Visão Geral

Este projeto implementa um pipeline de dados end-to-end no Databricks para processar, transformar e analisar dados de shows e turnês do grupo Stray Kids. O objetivo é fornecer insights sobre padrões geográficos, temporais e de venues, além de predições para futuros eventos.

## Arquitetura do Projeto

### Camadas de Dados

O projeto segue a arquitetura medallion (bronze → silver → gold):

```
skztour/
├── 01_landing/     # Camada bronze: dados brutos
├── 02_silver/      # Camada silver: dados limpos e padronizados
└── 03_gold/        # Camada gold: dados agregados e prontos para consumo
    └── shows_unified  # Tabela principal unificada
```

### Estrutura do Repositório

```
skz_tour_analysis/
├── notebooks/
│   ├── 01_landing/    # Notebooks de ingestão de dados
│   └── 02_silver/     # Notebooks de transformação
├── dashboards/        # Configurações de dashboards
└── README.md
```

## Fontes de Dados

### Coleta de Dados

Os dados deste projeto foram obtidos através de **web scraping** das seguintes fontes:

- **[Setlist.fm](https://www.setlist.fm/)** - Informações sobre datas de shows, locais e setlists
- **[Wikipedia](https://pt.wikipedia.org/)** - Dados complementares sobre turnês e venues

### Importante: Dados Sintéticos

**Este projeto utiliza dados parcialmente sintéticos para fins educacionais.** 

Devido à incompletude das fontes originais (setlist.fm e Wikipedia), alguns dados foram gerados ou complementados artificialmente para viabilizar a análise completa. Portanto:

- O projeto demonstra técnicas de engenharia de dados e análise
- A arquitetura e pipeline são reais e funcionais
- **Os resultados NÃO refletem 100% a realidade dos shows do Stray Kids**
- Dados de capacidade de venues, algumas datas e localizações podem ser aproximados

Este é um projeto de **portfólio educacional** que exemplifica um pipeline completo de dados.

## Dashboard Interativo

O projeto inclui um dashboard multi-página com análises detalhadas:

### Páginas do Dashboard

1. **Geographic Analysis** 
   - Distribuição de shows por país e cidade
   - Mapas de calor de concentração de eventos
   - Análise de cobertura geográfica

2. **Temporal Analysis** 
   - Evolução temporal dos shows
   - Padrões sazonais e tendências
   - Frequência de eventos ao longo do tempo

3. **Venue Analysis** 
   - Análise de capacidade dos venues
   - Tipos de locais mais utilizados
   - Distribuição por tamanho de arena

4. **Predictions** 
   - Projeções para futuros shows
   - Análise preditiva de localizações
   - Tendências e insights estratégicos

## Como Usar

### Pré-requisitos

- Workspace Databricks (AWS)
- Acesso ao Unity Catalog
- Permissões para criar tabelas no schema `skztour`

### Executar o Pipeline

1. **Processar dados brutos (Landing)**
   ```
   Execute os notebooks em: notebooks/01_landing/
   ```

2. **Transformar para Silver**
   ```
   Execute os notebooks em: notebooks/02_silver/
   ```

3. **Tabela Gold será criada automaticamente**
   ```
   Tabela final: skztour.03_gold.shows_unified
   ```

4. **Visualizar no Dashboard**
   - Abra o dashboard "Stray Kids Concert Analysis" no Databricks

## Dados Processados

A tabela principal `skztour.03_gold.shows_unified` contém:
- Datas e localizações de shows
- Informações de venues (nome, capacidade, tipo)
- Dados geográficos (país, cidade, coordenadas)
- Métricas agregadas e calculadas

## Tecnologias Utilizadas

- **Databricks**: Plataforma de processamento
- **Apache Spark**: Engine de processamento distribuído
- **Delta Lake**: Armazenamento otimizado
- **Unity Catalog**: Governança de dados
- **Lakeview**: Dashboards interativos
- **Python/SQL**: Linguagens de desenvolvimento

## Próximos Passos

- [ ] Adicionar dados de vendas de ingressos
- [ ] Implementar análise de sentimento de redes sociais
- [ ] Criar modelo de ML para predição de demanda
- [ ] Automatizar pipeline com Databricks Jobs
- [ ] Adicionar testes unitários

## Contribuindo

Este é um projeto pessoal de análise de dados. Sugestões e melhorias são bem-vindas!

## icença

Este projeto é de uso **educacional e analítico**. Os dados foram coletados de fontes públicas (setlist.fm e Wikipedia) e complementados com dados sintéticos para fins didáticos.



