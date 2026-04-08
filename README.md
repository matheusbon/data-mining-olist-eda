# EDA — Brazilian E-Commerce (Olist)

Análise Exploratória de Dados do dataset público da Olist, seguindo a **Fase 2 do CRISP-DM**.

## Dataset

[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — disponível no Kaggle.

## Como baixar os dados

Com o Kaggle CLI configurado (`~/.kaggle/kaggle.json`):

```bash
kaggle datasets download -d olistbr/brazilian-ecommerce --unzip -p data/
```

## Estrutura do projeto

```
.
├── eda_olist.ipynb          # Notebook principal de EDA
├── data/                    # Datasets (não versionados)
└── Aula - Fase 2 do CRISP-DM #crispdm.pdf
```

## Conteúdo do notebook

| Seção | Descrição |
|---|---|
| 1. Carregamento | Leitura dos 8 CSVs |
| 2. Visão Geral | Exploração das tabelas principais |
| 3. Dataset Principal | Merge e definição da variável-alvo (`delivery_late`) |
| 4. Train/Test Split | Separação 80/20 antes de qualquer análise |
| 5. Valores Ausentes | Heatmap e quantificação de NaNs |
| 6. Variáveis Numéricas | Estatísticas descritivas e histogramas |
| 7. Variáveis Categóricas | Distribuição de status, pagamento, estados e categorias |
| 8. Categorias vs Target | Relação entre categorias e atraso na entrega |
| 9. Categorias vs Numérico | Boxplots por tipo de pagamento e avaliação |
| 10. Análise Temporal | Pedidos por mês, dia da semana e hora |
| 11. Correlações | Heatmap de correlação entre variáveis numéricas |

## Dependências

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
