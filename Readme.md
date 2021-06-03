# **Detecção de Fraudes em Cartões de Crédito**

<p align=center>
<img src="http://sigmoidal.ai/wp-content/uploads/2019/12/900.jpg" width="%"></p>

### 1. Projeto:
Neste projeto iremos abordar o problema das fraudes bancárias em cartões de crédito. Umda das principais preocupações das instituições financeirs como bancos e *fintechs*. Apenas no Brasil, ceca de 12,1 milhões de pessoas já foram vítimas de altum tipo de fraude financeira no último ano. Trauduzindo em valores, os golpes financeiros ultrapassaram a cifra de 1,8 bilhão de prejuízo por ano.

Dentro desse escopo, as fraudes envolvendo cartões de crédito são de grande relevância. A não detecção dessas fraudes acarreta prejuízos para consumidores e instituições financeiras.

Por os motivos expostos acima, o investimento em algoritmos que trabalhem na área de detecção de fraudes vem crescendo a cada ano, representando uma grande oportunidade para os estudiosos em Data Science.

Levando-se em conta os vultuoso valores fraudados, então um algoritmo de *machine learning* que melhore somente um pouco, os anteriores, isso já representa uma economia de milhões de Reais.

### 2. Dados:

O DataFrame disponibilizado possui 31 variáveis e 284.807 entradas.

Porém, além das variáveis ```Time``` (tempo em segundos), ```Amount``` (valor da transação) e ```Class``` (alvo), o Dataframe possui 28 variáveis numéricas, que foram propositadamente ocultadas, sob a nomenclatura de V1 a V28 $[V1, V2, V3 \dots, V28]$, por motivos ligados à privacidade e segurança. 

### 3. Objetivos/Tarefas:

O projeto foi dividido em 4 objetivos, sendo 1 descritivo e 3 decorrente da utilização de modelos de machine learning:

1. Balancear das classes normal e fraude;
2. Padronizar as classes ```Time``` e ```Amount``` para adequá-las às demais variáveis;
3. Por que as variáveis, principalmente as variáveis denominadas de V1 a V28, não possuem correlação entre si?
4. Qual a probabilidade de se identificar uma operação fraudulenta, utilizando a melhor otimização de algoritmo?

### 4. Aspecto dos Dados:

A variável ```Time``` representa as operações financeiras que aconteceram no período de dois dias. Esse tempo é contado em segundos, ou seja, vai do segundo 0.0 ao segundo 172792.0.

Como já foi dito anteriormente, a variável ```Amount``` representa o valor da transação que varia de 0.0 a 25691.16, esta seria a operação mais onerora.

Então temos variáveis numéricas com nomenclatura entre V1 e V28.  Essas variáveis passaram por uma transformação conhecida como Análise de Componentes Principais (*Principal Component Analysis* - PCA) para reduzir a dimensionalidade  ao mesmo tempo que mantém o maior número possível de informações.

Por fim a  variável alvo possui dois valores booleanos onde:
* 0: Representa uma transação normal; e 
* 1: Representa uma transação fraudulenta.

Entretanto, dentro de um total de 284.807 operações, somente foram classificadas como fraudulentas 492 operaçoes, o que corresponde a 0,17% do total.

### 5. Conclusões:

1. O balanceamento dos dados na variável alvo fez com que a aparente falta de correlação entre as variáveis V1 e V28, mostrarem-se correlacionadas, demonstrando que a fakta de correlação foi uma consequência do grande desbalanceamento;
2. Tendo em vista o montante de operações processadas na  DataFram de teste, 85443, das quais somente ```148 (0,17%)``` eram fraudes, o sistema conseguiu identificar com exatidão ```132 (89,19%)``` sacrificando um total de ```2299``` operações normais que foram consideradas fraudadas, o que corresponde a ```2,69%``` das operações normais. O que pode ser considerado um resultado excelente obtido pelo algoritmo criado, tendo em vista que a capacidade de distinção entre as classes medida pelo AUC ROC é de ```0.964```.