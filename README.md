# 📊 Decifrando o Cliente: o que faz uma campanha ser aceita?

**Análise exploratória multivariada e testes de hipótese para entender quais clientes respondem a campanhas de marketing**

---

## 📌 Resumo

Uma empresa de varejo fez seis campanhas de marketing e quer entender por que alguns clientes aceitam as ofertas e outros as ignoram.

Com 2.237 clientes, o projeto mostra que **renda e volume de gastos** diferenciam com clareza quem aceita campanhas de quem não aceita. Já o **tempo de relacionamento** com a empresa não mostrou diferença estatística. A recomendação é segmentar as campanhas pelo comportamento de compra, e não pela antiguidade do cliente.

| Indicador | Resultado |
|---|---|
| Clientes analisados | 2.237 |
| Clientes que aceitaram alguma campanha | 27% |
| Campanha com maior aceitação | Campanha 6 (15,1%) |
| Campanha com menor aceitação | Campanha 5 (1,4%) |

---

## 🎯 Pergunta de negócio

> Quais fatores explicam a aceitação de campanhas de marketing pelos clientes?

Desdobramentos:
1. Clientes que aceitam campanhas têm renda diferente dos que não aceitam?
2. O volume de gastos é diferente entre os dois grupos?
3. O tempo de relacionamento com a empresa influencia a aceitação?

---

## 🗂️ Dados

- **Arquivo:** `dados/dados_clientes.csv`, com 2.237 clientes e 25 variáveis.
- **Perfil:** ano de nascimento, escolaridade, estado civil, renda (em US$), crianças e adolescentes em casa e data de cadastro.
- **Comportamento:** gastos por categoria (vinhos, frutas, carnes, peixes, doces e outros) e número de compras por canal (web, catálogo, loja e promoções).
- **Resposta:** aceitação de cada uma das 6 campanhas (0 ou 1).
- **Origem:** base fornecida em curso de Ciência de Dados, usada aqui para fins educacionais.

---

## 🛠️ Metodologia

```
Limpeza → Feature engineering → EDA → Ranking exploratório de fatores → Teste de normalidade → Testes de hipótese → Recomendações
```

1. **Limpeza e preparação:** padronização dos nomes das colunas, conversão da renda e das datas e remoção de outliers pelo método IQR. Essa etapa também excluiu os 24 registros sem renda informada.
2. **Feature engineering:** variáveis como `total_gastos` e `dias_como_cliente`.
3. **Análise exploratória:** taxas de aceitação por campanha, comportamento de compra e perfil dos clientes.
4. **Ranking exploratório de fatores:** importância de variáveis com Random Forest, usada apenas para priorizar o que testar.
5. **Normalidade:** teste de Shapiro-Wilk. As variáveis não seguem distribuição normal, por isso foi usado um teste não paramétrico.
6. **Testes de hipótese:** Mann-Whitney U, comparando quem aceitou e quem não aceitou campanhas.

---

## 📈 Resultados dos testes de hipótese

| Variável | p-valor | Conclusão (α = 0,05) |
|---|---|---|
| `total_gastos` | 2,91 × 10⁻⁶⁶ | ✅ Diferença significativa entre os grupos |
| `renda` | 7,99 × 10⁻⁴³ | ✅ Diferença significativa entre os grupos |
| `dias_como_cliente` | 0,33 | ❌ Sem diferença significativa |

---

## 💡 Insights para o negócio

- **Priorizar clientes com maior renda e maior histórico de gastos.** São os perfis com maior propensão a aceitar ofertas.
- **Não usar o tempo de casa como critério de segmentação.** Clientes antigos e novos respondem de forma parecida.
- **Estudar o que diferenciou a campanha 6 da campanha 5.** A taxa de aceitação variou mais de dez vezes entre elas, o que indica que oferta, canal e momento pesam tanto quanto o perfil do cliente.

---

## 📝 Escopo da análise

- O estudo é explicativo, não preditivo: identifica fatores associados à aceitação, sem afirmar relação de causa.
- O ranking da Random Forest serviu para priorizar as variáveis testadas; não é um modelo de previsão.

---

## ▶️ Como reproduzir

```bash
git clone https://github.com/RicardodeSouzaSilva/Projeto_Multivariada_Para_a_Area_de_Marketing.git
cd Projeto_Multivariada_Para_a_Area_de_Marketing
pip install -r requisitos.txt
jupyter notebook Decifrando_o_Cliente_O_Que_Faz_uma_Campanha_Ser_Aceita.ipynb
```

---

## 📁 Estrutura

```
├── dados/
│   └── dados_clientes.csv
├── Decifrando_o_Cliente_O_Que_Faz_uma_Campanha_Ser_Aceita.ipynb   # notebook principal
├── Relatorio_Estrategico_Decifrando_o_Cliente_O_Que_Faz_uma_Campanha_Ser_Aceita.pdf   # relatório executivo
├── requisitos.txt
├── LICENSE
└── README.md
```

---

## 🧰 Stack

Python · Pandas · NumPy · SciPy · scikit-learn · Matplotlib · Seaborn · Missingno

---

## 👤 Autor

**Ricardo de Souza Silva** · Data Scientist | Data Analytics | Business Intelligence

[LinkedIn](https://www.linkedin.com/in/ricardo-de-souza-silva/) · [GitHub](https://github.com/RicardodeSouzaSilva)
