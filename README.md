# Análise Estatística Aplicada ao Controle de Qualidade de Vinhos📊

Este repositório/notebook contém as instruções e os códigos necessários para reproduzir a análise estatística descritiva e inferencial aplicada ao banco de dados Wine Quality, focando no controle de qualidade na indústria alimentícia e enológica.

O projeto explora o uso integrado das distribuições contínuas (Normal, t de Student, Qui-Quadrado e F de Fisher) para realizar inferências populacionais, avaliar a estabilidade de processos e comparar variabilidades entre lotes distintos (Vinho Tinto vs. Vinho Branco).

---

## 👥 Integrantes do Grupo (Ordem Alfabética)

- **[Lais Zanquettim Stocco Teixeira - 14586772]**
- **[Mariana Lopes Marques -14596593]**
- **[Nayara Penati - 15677365]** 

---

## 📂 Conjunto de Dados (Dataset)
Os dados utilizados pertencem ao Wine Quality Dataset (disponível no UCI Machine Learning Repository). O projeto requer os seguintes arquivos para a execução:
- winequality-red.csv: Dados físico-químicos do vinho tinto (1599 instâncias)
- winequality-white.csv: Dados físico-químicos do vinho branco (4898 instâncias).

---

## 🛠️️ Pré-requisitos e Bibliotecas
Para executar a análise em um ambiente local (caso não utilize o Google Colab), é necessário ter o Python 3.7+ instalado, além das seguintes bibliotecas de Ciência de Dados:

pip install pandas numpy scipy matplotlib

---

## 📊 Estrutura da Análise
A análise está dividida em quatro grandes módulos estatísticos, cada um respondendo a problemas específicos do chão de fábrica e do controle de qualidade:
1. Distribuição Normal
-  Objetivo: Estabelecer o modelo de referência e as especificações ideais do produto.
-  Implementação: Cálculo da Função Densidade de Probabilidade (FDP) para o atributo pH, variação paramétrica ($\mu$ e $\sigma$), determinação de probabilidades (acumulada, intervalar, cauda) e cálculo de percentis com plotagem de áreas sombreadas.
2. Distribuição t de Student
- Objetivo: Avaliar hipóteses sobre a média amostral de características físico-químicas (como a acidez fixa) quando o desvio-padrão populacional é desconhecido
- Implementação: Demonstração do comportamento das caudas pesadas em amostras reduzidas e acomodação da incerteza amostral.
3. Distribuição Qui-Quadrado
- Objetivo: Modelar e testar a variabilidade de medições individuais em um único processo (ex: oscilação do teor alcoólico no envasamento).
- Implementação: Avaliação da atenuação da assimetria da curva com o aumento do tamanho da amostra (graus de liberdade).
4. Distribuição F de Fisher
- Objetivo: Comparar a variabilidade estatística entre duas linhas independentes.
- Implementação: Teste de hipóteses comparando a variância da acidez fixa entre o grupo do Vinho Tinto ($df_1 = 1598$) e o Vinho Branco ($df_2 = 4897$), incluindo cálculos de percentil crítico ($P_{95}$) e visualização das zonas de aceitação/rejeição.

---

## 🚀 Como Reproduzir a Análise
- Via Ambiente Local (Jupyter Notebook / Script Python)
  1. Faça o download dos arquivos CSV e coloque-os na mesma pasta do seu script Python ou arquivo .ipynb.
  2. Copie os blocos de código gerados ao longo deste projeto referentes aos gráficos da Distribuição Normal e F de Fisher.
  3. Execute o script sequencialmente. O código buscará automaticamente os arquivos .csv no diretório raiz ou subpastas por meio do módulo os.
  4. Os gráficos serão gerados interativamente via matplotlib.pyplot.show().

---


## 🛠️ Bibliotecas Utilizadas
pandas: Utilizada para a leitura, estruturação e manipulação dos bancos de dados em formato CSV (pd.read_csv), bem como para o cálculo das variâncias e médias diretamente das colunas (ex: df['pH'].mean()).

scipy (especificamente o módulo scipy.stats): O motor estatístico do projeto. Forneceu as funções para trabalhar com as distribuições teóricas (Normal, F de Fisher, etc.), permitindo calcular a densidade de probabilidade (pdf), probabilidades acumuladas (cdf), probabilidades de cauda (sf) e percentis críticos (ppf).

numpy: Empregada para a geração de arrays e sequências numéricas (através da função np.linspace), essenciais para definir o eixo horizontal (X) na plotagem das curvas contínuas.

matplotlib (especificamente matplotlib.pyplot): Responsável pela criação e formatação de todos os gráficos, permitindo desenhar as curvas, criar múltiplos painéis (subplots) e colorir as áreas sombreadas sob a curva de probabilidade (fill_between).

os e zipfile: Bibliotecas nativas da linguagem utilizadas para interagir com o sistema de arquivos, extrair a base de dados do arquivo ZIP e localizar os arquivos CSV de forma automática, evitando erros de caminho de diretório.

---

## 📚 Referências Bibliográficas e Fontes de Dados
https://archive.ics.uci.edu/dataset/186/wine+quality

https://www.inf.ufsc.br/~andre.zibetti/probabilidade/normal.html

BUSSAB, Wilton de O.; MORETTIN, Pedro A. Estatística Básica. 9. ed. São Paulo: Saraiva, 2017.

CORTEZ, Paulo; CERDEIRA, António; ALMEIDA, Fernando; MATOS, Telmo; REIS, José. Wine Quality. UCI Machine Learning Repository, 2009.

MONTGOMERY, Douglas C.; RUNGER, George C. Estatística Aplicada e Probabilidade para Engenheiros. 7. ed. Rio de Janeiro: LTC, 2018.)
