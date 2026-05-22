```markdown
# 🛡️ You Shall Not sPam: Esteira de ML para Detecção de Spam

Este projeto implementa uma esteira de **Machine Learning (ML)** completa voltada para a classificação binária de e-mails, determinando se uma mensagem é legítima (Ham) ou indesejada (Spam). O projeto foi desenvolvido em Python estruturado em um Jupyter Notebook (`.ipynb`), seguindo os moldes e a estrutura de código propostos em aula.

O codinome do projeto é inspirado no universo geek: assim como o mago Gandalf barra as forças das trevas, nossa esteira barra os spams com o lema **"You Shall Not sPam!"**.

---

## 🚀 Estrutura da Esteira (Pipeline)

A esteira foi projetada de forma autônoma e robusta, dividida rigorosamente nas seguintes etapas (cumprindo todos os requisitos estabelecidos):

1. **Carga de Dados & Análise Descritiva:** Download 100% automatizado do dataset *Spambase* via requisição HTTP (`requests`) diretamente do repositório oficial da UCI. Exibição imediata das estatísticas descritivas gerais das variáveis (Média, Desvio Padrão, Máximos e Mínimos).
2. **Transformação de Colunas:** Aplicação de normalização de escala por Z-score utilizando o `StandardScaler` do Scikit-Learn nas variáveis contínuas, colocando todos os atributos na mesma escala para otimização do aprendizado do modelo.
3. **Transformação de Linhas:** Limpeza avançada da base de dados através da detecção e remoção completa de linhas duplicadas, blindando o modelo contra problemas de vazamento de dados (*data leakage*) e overfitting.
4. **Divisão de Dados:** Particionamento estratificado (`stratify`) da base em três subconjuntos bem definidos para garantir a consistência das proporções das classes:
   * **Treinamento:** 70% dos dados.
   * **Validação:** 15% dos dados (usado para ajuste e monitoramento).
   * **Testes:** 15% dos dados (retidos para a avaliação final e inédita).
5. **Treinamento do Modelo:** Instanciação e treinamento de um classificador de Floresta Aleatória (*Random Forest Classifier*) com semente de reprodutibilidade fixa (`random_state=42`).
6. **Avaliação de Performance:** Geração automática da métrica de acurácia global do modelo, Relatório de Classificação detalhado (Precision, Recall e F1-Score) e exibição visual e gráfica de uma Matriz de Confusão com o suporte do `Seaborn`.
7. **Predição Implantada:** Simulação real do funcionamento do modelo em "produção" através de uma predição unitária e isolada, exibindo as probabilidades matemáticas calculadas para o e-mail em análise.

---

## 🛠️ Pré-requisitos

Antes de rodar o projeto, certifique-se de ter instalado as seguintes bibliotecas no seu ambiente Python (como Anaconda ou ambiente virtual):

```bash
pip install pandas numpy requests scikit-learn matplotlib seaborn

```

---

## 📖 Tutorial de Uso

Siga os passos abaixo para executar a esteira no seu ambiente:

### Passo 1: Abrir o Ambiente

Abra o arquivo `.ipynb` do projeto em seu ambiente **Jupyter Notebook**, **JupyterLab** ou **Google Colab**.

### Passo 2: Executar as Células de Carga e Preparação

Execute as primeiras células de código. O script buscará de forma transparente o arquivo ZIP da UCI na internet, descompactará o arquivo `spambase.data` diretamente na memória RAM, organizará as colunas nomeadas, exibirá os sumários estatísticos e aplicará as transformações necessárias de colunas e linhas.

### Passo 3: Divisão e Treinamento do Modelo

Rode as células de particionamento e treinamento. O algoritmo *Random Forest* analisará os padrões estatísticos de frequência de palavras comuns em e-mails maliciosos (termos como "free", "money", "credit") e características de uso de letras maiúsculas.

### Passo 4: Avaliar os Resultados (Métricas)

A célula de avaliação exibirá a Acurácia Final do modelo no conjunto de testes e plotará o mapa de calor (Heatmap) da Matriz de Confusão:

* **Verdadeiros Negativos (E-mails normais legítimos):** Classificados corretamente.
* **Verdadeiros Positivos (Spams detectados):** Bloqueados com sucesso pelo sistema.

### Passo 5: Testar a Predição de Produção

A última célula executa o teste de um e-mail isolado. A saída no terminal trará a validação do modelo com este formato explicativo:

```text
--- Executando Predição Unitária ---
E-mail indexado analisado pelo sistema.
Probabilidade de NÃO ser Spam: XX.XX%
Probabilidade de SER Spam: XX.XX%
Resultado da classificação da IA: [SPAM / E-MAIL CONFIÁVEL]
Gabarito real (Validação Humana): [SPAM / E-MAIL CONFIÁVEL]

```

---

## 🧬 Tecnologias Utilizadas

* **Python 3.12+**
* **Requests & Zipfile:** Para coleta dinâmica do arquivo diretamente do repositório da web sem necessidade de downloads manuais prévios.
* **Pandas & NumPy:** Manipulação matricial, limpeza de registros e engenharia de dados.
* **Scikit-Learn:** Divisão estratificada da base, normalização de atributos (`StandardScaler`), modelo preditivo (`RandomForestClassifier`) e cálculo de métricas de classificação.
* **Matplotlib & Seaborn:** Geração de gráficos, estilização visual de matrizes e mapas de calor de performance.

```

```