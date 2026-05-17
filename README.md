# 🛡️ You Shall Not sPam: Esteira de ML para Detecção de Spam

Este projeto implementa uma esteira de **Machine Learning (ML)** completa voltada para a classificação binária de e-mails, determinando se uma mensagem é legítima (Ham) ou indesejada (Spam). O projeto foi desenvolvido em Python estruturado em um Jupyter Notebook (`.ipynb`).

O codinome do projeto é inspirado no universo geek: assim como o mago Gandalf barra as forças das trevas, nossa esteira barra os spams com o lema **"You Shall Not sPam!"**.

---

## 🚀 Estrutura da Esteira (Pipeline)

A esteira foi projetada seguindo as melhores práticas da engenharia de dados e modelagem preditiva, dividida nas seguintes etapas:

1. 
**Carga de Dados & Análise Descritiva:** Download automatizado do dataset *Spambase* do repositório UCI e exibição de métricas estatísticas das variáveis.


2. **Transformação de Linhas:** Limpeza de dados com a remoção de registros duplicados para evitar vazamento de dados (*data leakage*).
3. 
**Transformação de Colunas:** Normalização de escala com *Z-score* (`StandardScaler`) nas 57 variáveis contínuas (frequência de palavras e caracteres).


4. **Divisão de Dados:** Particionamento da base nos três subconjuntos essenciais: **Treino (60%)**, **Validação (20%)** e **Teste (20%)**.
5. **Treinamento do Modelo:** Ajuste de um classificador de Floresta Aleatória (*Random Forest Classifier*).
6. **Avaliação Fina:** Geração automática da Acurácia, Relatório de Classificação e exibição visual de uma Matriz de Confusão.
7. **Predição em Produção:** Simulação de um e-mail real passando pela esteira para obter a classificação final em tempo real.

---

## 🛠️ Pré-requisitos

Antes de rodar o projeto, certifique-se de ter instalado as seguintes bibliotecas Python:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn

```

---

## 📖 Tutorial de Uso

Siga os passos abaixo para executar a esteira no seu ambiente:

### Passo 1: Abrir o Ambiente

Abra o arquivo `.ipynb` do projeto no **Google Colab** ou em seu ambiente **Jupyter Notebook** local.

### Passo 2: Executar as Células de Preparação

Execute as primeiras células para baixar a base de dados original  e aplicar o pré-processamento (limpeza de linhas duplicadas e normalização das colunas).

### Passo 3: Treinar o Modelo

Rode a célula de treinamento. O algoritmo *Random Forest* analisará os padrões de frequência de termos comuns em spams (como "free", "money", e excesso de letras maiúsculas).

### Passo 4: Avaliar os Resultados

A célula de avaliação exibirá um gráfico da Matriz de Confusão parecido com este:

* **Verdadeiros Negativos:** E-mails legítimos classificados corretamente.
* 
**Verdadeiros Positivos:** Spams bloqueados com sucesso.



### Passo 5: Testar uma Predição Única

A última célula da esteira escolherá um e-mail aleatório para testar o modelo. A saída no seu terminal será parecida com isto:

```text
--- Simulação de Entrada de Novo E-mail na Esteira ---
Resultado Real do E-mail selecionado: Spam
Resultado da Predição do Modelo: Spam
Probabilidade de ser Não-Spam: 1.00% | Probabilidade de ser Spam: 99.00%

```

---

## 🧬 Tecnologias Utilizadas

* **Python 3.12+**
* **Pandas & NumPy:** Manipulação e limpeza dos dados.
* **Scikit-Learn:** Engenharia de atributos, divisão da base e algoritmos de ML.
* **Matplotlib & Seaborn:** Visualização de dados e gráficos de desempenho.
