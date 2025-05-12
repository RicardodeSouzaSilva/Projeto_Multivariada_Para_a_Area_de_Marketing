
# 📊 Decifrando o Cliente: O Que Faz uma Campanha Ser Aceita?

Este projeto busca identificar os fatores que influenciam os clientes a aceitarem campanhas de marketing. Utilizando ciência de dados e testes estatísticos, o estudo oferece **insights acionáveis** para estratégias comerciais mais eficazes.

---

## 🧠 Objetivos

- Analisar variáveis que influenciam a aceitação de campanhas.
- Verificar estatisticamente as diferenças entre os perfis de clientes.
- Gerar recomendações com base em evidências para aumentar a taxa de conversão.

---

## 🛠️ Metodologia

1. **Análise Exploratória de Dados (EDA)**  
2. **Seleção de Variáveis com Floresta Aleatória**  
3. **Verificação de Normalidade com Shapiro-Wilk**  
4. **Testes de Hipóteses com Mann-Whitney U**

---

## 📈 Principais Resultados

| Variável             | Resultado | Interpretação |
|----------------------|-----------|---------------|
| `renda`              | ✅ Significativo | Diferença entre os grupos |
| `total_gastos`       | ✅ Significativo | Influência direta no comportamento |

---

## 💡 Insights para o Negócio

- 📌 **Segmentar clientes com maior renda e histórico de gastos.**  
- 📌 **Rever critérios baseados apenas no tempo de relacionamento.**  
- 📌 **Focar campanhas em perfis com maior propensão à resposta.**

---

## 📁 Estrutura do Projeto

```
decifrando_campanha/
├── dados_clientes.csv
├── analise_estatistica.ipynb
├── README.md
└── requisitos.txt
```

---

## ⚙️ Requisitos

- Python 3.12+
- Bibliotecas:
  - pandas==2.2.2
  - numpy==1.26.4
  - matplotlib==3.8.4
  - seaborn==0.13.2
  - scikit-learn==1.4.2
  - scipy==1.13.1
  - missingno==0.5.2

Instale via:

```bash
pip install -r requisitos.txt
```

---

## 👨‍💻 Autor

**Ricardo**  
Data Scientist | Estatística Aplicada | Marketing Analytics
