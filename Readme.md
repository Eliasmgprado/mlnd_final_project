
# Machine Learning Engineer Nanodegree - Udacity
## Projeto Final

# Machine Learning na Classificação de Rochas Vulcânicas

Neste trabalho é proposto a avaliação da utilização dos métodos de aprendizado de máquina para discriminar a litologia (tipo de rocha) a partir de dados de química de rocha. Pretende-se avaliar o desempenho na classificação litológica dos principais algoritmos de classificação supervisionada utilizados atualmente (Support Vector Classifier-SVC, K-Nearest Neighbors Classifier-KNN, Random Forest Classifier-RF e Xgboost).

O algoritmo será desenvolvido para executar uma tarefa de classificação multi-label, recebendo como entrada dados estruturados, contendo as análises químicas de amostras de rocha, e retornando como saída o nome da rocha com a maior probabilidade (similaridade) dentre os vários nomes possíveis.

[Link para proposta do projeto final](https://review.udacity.com/#!/reviews/878486)

### Repositorio

O projeto está disponivel para download no [Github](https://github.com/Eliasmgprado/mlnd_final_project). Para clonar o projeto use o comando abaixo.

```bash
$git clone https://github.com/Eliasmgprado/mlnd_final_project
```

### Prerequisitos

* [pandas](https://pandas.pydata.org/) 
* [numpy](http://www.numpy.org/)
* [seaborn](https://seaborn.pydata.org/)
* [missingno](https://github.com/ResidentMario/missingno)
* [matplotlib](https://matplotlib.org/)
* [scikitlearn](http://scikit-learn.org/stable/index.html)
* [xgboost](http://xgboost.readthedocs.io/en/latest/)
* [mlxtend](https://github.com/rasbt/mlxtend)


Todos estes modulos podem ser instalados utilizando o pip ou conda

```bash
$pip intall pandas numpy seaborn missigno matplotlib sklearn xgboost mlxtend
```
```bash
$conda intall pandas numpy seaborn missigno matplotlib sklearn xgboost mlxtend
```

### Dados

Os dados utilizados foram extraídos do banco de dados petrológico [GEOROC](http://georoc.mpch-mainz.gwdg.de/georoc/).

Segue link para baixar os arquivos utilizados:

* [ALDAN SHIELD - ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/ALDAN_SHIELD_-_ARCHEAN.csv)
* [AMAZONIA CRATON.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/AMAZONIA_CRATON.csv)
* [BALTIC SHIELD - ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/BALTIC_SHIELD_-_ARCHEAN.csv)
* [BASTAR CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/BASTAR_CRATON_ARCHEAN.csv)
* [CHURCHILL PROVINCE ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/CHURCHILL_PROVINCE_ARCHEAN.csv)
* [DHARWAR CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/DHARWAR_CRATON_ARCHEAN.csv)
* [GAWLER CRATON.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/GAWLER_CRATON.csv)
* [KAAPVAAL CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/KAAPVAAL_CRATON_ARCHEAN.csv)
* [NORTH ATLANTIC CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/NORTH_ATLANTIC_CRATON_ARCHEAN.csv)
* [NORTH CHINA CRATON.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/NORTH_CHINA_CRATON.csv)
* [RAE CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/RAE_CRATON_ARCHEAN.csv)
* [SAO FRANCISCO CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SAO_FRANCISCO_CRATON_ARCHEAN.csv)
* [SARMATIAN CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SARMATIAN_CRATON_ARCHEAN.csv)
* [SIBERIAN CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SIBERIAN_CRATON_ARCHEAN.csv)
* [SINGHBHUM CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SINGHBHUM_CRATON_ARCHEAN.csv)
* [SLAVE PROVINCE ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SLAVE_PROVINCE_ARCHEAN.csv)
* [SUPERIOR PROVINCE ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/SUPERIOR_PROVINCE_ARCHEAN.csv)
* [TANZANIA CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/TANZANIA_CRATON_ARCHEAN.csv)
* [UKRAINIAN SHIELD ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/UKRAINIAN_SHIELD_ARCHEAN.csv)
* [WEST AFRICAN CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/WEST_AFRICAN_CRATON_ARCHEAN.csv)
* [WEST AUSTRALIAN CRATON.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/WEST_AUSTRALIAN_CRATON.csv)
* [ZIMBABWE CRATON ARCHEAN.csv](http://georoc.mpch-mainz.gwdg.de/georoc/Csv_Downloads/Archean_Cratons_comp/ZIMBABWE_CRATON_ARCHEAN.csv)


### Detalhes

Os Arquivos principais do projeto são:

* [Projeto_Final_EML](https://github.com/Eliasmgprado/mlnd_final_project/blob/master/Projeto_Final_EML.ipynb) - [jupyter notebook](http://jupyter.org/) do projeto 
* [Projeto_final](https://github.com/Eliasmgprado/mlnd_final_project/blob/master/Projeto_final.pdf) - Relatório do projeto

### Autor

* **Elias Martins Guerra Prado** - *Github* - [Eliasmgprado](https://github.com/Eliasmgprado)

### Agradecimentos

* [Udacity](https://br.udacity.com/)



```python

```
