# EDA — Previsão de Satisfação do Cliente (Olist)

## Contexto e Domínio

Dataset público da [Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) com dados reais e anonimizados de compras realizadas em marketplaces brasileiros entre **2016 e 2018**, cobrindo pedidos por diferentes perspectivas: status, pagamento, frete, clientes, produtos e avaliações.

## Problema de Negócio

**Prever a nota de satisfação do cliente** após uma compra, para que a empresa consiga identificar pedidos com maior risco de gerar avaliações ruins e atuar preventivamente — melhorando logística, atendimento e reputação dos vendedores.

Avaliações negativas impactam confiança, recompra e percepção de qualidade do marketplace.

## Variável-Alvo

| Coluna | Tipo | Classes |
|---|---|---|
| `review_score` | Classificação multiclasse | 1, 2, 3, 4 e 5 estrelas |

## Critério de Sucesso

O modelo seria útil se conseguisse **antecipar pedidos com alta chance de receber 1 ou 2 estrelas**, permitindo ação preventiva: contato proativo com o cliente, priorização de suporte ou correção de problemas de entrega.

## Considerações Éticas

- Não responsabilizar exclusivamente vendedores por notas baixas causadas por transportadoras ou atrasos externos
- Monitorar viés por categoria de produto, região ou perfil de vendedor
- Decisões automatizadas devem ter explicabilidade adequada para parceiros comerciais

---

## Como Baixar os Dados

Com o Kaggle CLI configurado (`~/.kaggle/kaggle.json`):

```bash
kaggle datasets download -d olistbr/brazilian-ecommerce --unzip -p data/
```

## Estrutura do Projeto

```
.
├── eda_olist.ipynb                        # Notebook principal de EDA
├── Aula - Fase 2 do CRISP-DM #crispdm.pdf  # Material de referência
└── data/                                  # Datasets (não versionados)
```

## Conteúdo do Notebook

| Seção | Descrição |
|---|---|
| 1. Carregamento | Leitura dos 8 CSVs e overview de shapes |
| 2. Visão Geral | `.head()` das tabelas principais |
| 3. Dataset Principal | Merge + features derivadas (`delivery_late`, `delivery_time_days`) |
| 4. Train/Test Split | Separação 80/20 estratificada antes de qualquer análise |
| 5. Distribuição do Target | Análise de desbalanceamento do `review_score` |
| 6. Valores Ausentes | Heatmap e quantificação de NaNs |
| 7. Variáveis Numéricas | Estatísticas descritivas e histogramas |
| 8. Variáveis Categóricas | Status, pagamento, estados e categorias de produto |
| 9. Categorias vs Target | Boxplot e nota média por categoria/estado |
| 10. Logística vs Target | Impacto de atraso e tempo de entrega na nota |
| 11. Análise Temporal | Pedidos por mês, dia da semana e hora |
| 12. Correlações | Heatmap de correlação incluindo o target |
| Conclusões | Observações e próximos passos |

## Dependências

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
