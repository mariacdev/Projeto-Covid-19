# Projeto Cenário de Casos e Óbitos relacionados à COVID-19

![imagem covid-19](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/d4b4d65a-f884-4bbb-b7d4-3b79975806ff)

O surgimento da pandemia de COVID-19 representa um dos eventos mais marcantes do século XXI. Essa crise de saúde global teve início em 2019 com a detecção de casos de uma nova doença respiratória na cidade de Wuhan, na China. Em 11 de março de 2020, a OMS classificou a COVID-19 como uma pandemia.

O impacto dessa pandemia foi notável na saúde pública, na economia e na sociedade global. Conforme a Organização Mundial da Saúde (OMS), aproximadamente 770 milhões de pessoas foram infectadas pela COVID-19, resultando em cerca de 7 milhões de mortes ao redor do mundo.

Este projeto visa aprofundar a compreensão desse cenário por meio da análise de dados públicos sobre a COVID-19, abordando tanto os números globais quanto os específicos do Brasil. A análise concentrará sua atenção nos registros de óbitos e casos confirmados da doença. 

## Objetivo do Estudo

Realizar uma exploração nos dados públicos da COVID-19, abrangendo tanto as estatísticas globais como as específicas do Brasil. O objetivo principal desse levantamento foi analisar os registros de óbitos e casos confirmados da doença.

Todos os dados utilizados nesta análise foram adquiridos do conjunto de dados disponível no [GitHub](https://github.com/owid/COVID-19-data/tree/master/public/data).

## 1. Premissas do Estudo

Os atributos do conjunto de dados são:
![premissas](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/4bbe1cb4-87da-4ed3-9654-91c41769a931) 

**Para a limpeza dos dados:** 

Durante a análise, observou-se que os dados consolidados para continentes e regiões mais abrangentes do globo, como África, Ásia, Europa, União Europeia, América do Norte, Oceania e América do Sul, apresentam o prefixo "OWID_".

- Com o intuito de evitar redundâncias no data frame, o conjunto de dados da COVID-19 foi        segmentado em duas partes:

     "data_owid," que engloba os registros continentais;
     "data_new," que se dedica aos registros de países.

- Também identificaram-se alguns dados inconsistentes que comprometiam sua integridade. Com o propósito de assegurar a qualidade e confiabilidade dos resultados, procedeu-se com a 
 remoção desses dados incongruentes do conjunto.

### 2.	Ferramentas
- Python 3.10
- Jupyter Notebook
- Github
- Visual Studio Code
- Estatística: Média, Mediana e Desvio Padrão

## 3.	Insights dos dados 
Com análises realizadas, investiguei os casos que geraram insights interessantes:

## 4. Análise de Casos e Óbitos no Mundo

### 4.1. Primeiros Casos de COVID-19

Apesar de casos de uma nova doença respiratória terem sido detectados no final de 2019, os primeiros casos confirmados de COVID-19 foram registrados em 04/01/2020. Três países foram os primeiros a apresentar esses registros:

1. China;
2. Finlândia;
3. Alemanha.

![primeiro caso no mundo](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/7418d6b6-5e0e-419a-8ec7-003b3f637ad1)

### 4.2. Primeira Morte Registrada de COVID-19

A primeira morte ocorreu na China, no dia 12/01/2020.

![primeira morte na china](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/fcf97d96-6197-4acd-9899-a25d8cfe4ddc)

### 4.3. Valores Estatísticos

A seguir, aplicou-se o método .describe(), permitindo obter um resumo estatístico das variáveis numéricas presentes no dataset, com foco nas variáveis new_cases e new_deaths.

**Média e Desvio Padrão:**

- Para new_cases, a média é de aproximadamente 2499 novos casos diários, com um considerável desvio padrão de mais de 40 mil registros. Isso evidencia uma grande variabilidade nos números diários de novos casos;
- No caso de new_deaths, a média é de cerca de 22 novas mortes por dia, acompanhada de um desvio padrão de 152. Da mesma forma, nota-se uma variabilidade considerável nos números diários de novas mortes.

**Picos de Casos e Óbitos:**

Ambas as colunas apresentam valores máximos muito elevados, indicando picos significativos de novos casos e novas mortes em períodos específicos.

- Na coluna new_cases, o maior registro foi observado na China, em 23/12/2022 (abaixo há detalhes sobre esse registro);
- Quanto à coluna new_deaths, o maior número de óbitos registrado ocorreu no Chile, em 22/03/2022 (abaixo são fornecidas informações detalhadas sobre esse registro).

![valores estatísticos](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/706ff073-21c2-4ab5-82eb-bdd686e94ebe)

### 4.4. Correlação

A análise de correlação desempenha um papel crucial na compreensão das relações entre diversas variáveis de um conjunto de dados. Ao calcular a matriz de correlação, torna-se possível identificar o grau de associação linear entre diferentes pares de variáveis, variando de -1 (correlação negativa perfeita) a 1 (correlação positiva perfeita).

No contexto da investigação das estatísticas relacionadas à COVID-19, a matriz de correlação foi empregada para examinar quais variáveis apresentam uma relação mais significativa com o número total de óbitos registrados. Com base na tabela do diretor de Machine Learning do LinkedIn, Parvez Ahammad, observa-se abaixo que a maioria das relações possui uma alta correlação com a variável new_deaths:

| Size of Correlation         |	Interpretation                            |
| -------------------------   | ----------------------------------------- |
| .90 to 1.00 (-.90 to -1.00) | Very high positive (negative) correlation |
| .70 to .90 (-.70 to -.90)   | High positive (negative) correlation      |
| .50 to .70 (-.70 to -.50)   | Moderate positive (negative) correlation  |
| .30 to .50 (-.30 to -.50)   | Low positive (negative) correlation       |
| .00 to .30 (.00 to -.30)    | negligible correlation                    |

**Variações nas Mortes e Hospitalizações:**

Observa-se que a variável new_deaths apresenta uma correlação robusta com hosp_patients, icu_patients e weekly_hosp_admissions. Isso sugere que o aumento das mortes está associado ao aumento de pacientes hospitalizados, indicando possível pressão sobre os sistemas de saúde em momentos críticos.

**Óbitos e População**

A população também exibe correlação com o número de novas mortes, embora essa correlação seja mais fraca em comparação com as outras variáveis. Isso indica que o número de novas mortes tende a ser mais elevado em áreas com populações maiores, mas outros fatores também desempenham um papel importante.

É crucial destacar que correlação não implica causalidade. Mesmo diante de uma correlação forte entre duas variáveis, outros fatores não considerados podem influenciar ambas, criando uma relação aparente. Portanto, é essencial interpretar a correlação com cautela e considerar outras evidências antes de chegar a conclusões significativas.

![correlação](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/6f0a5dee-a0c2-4fc5-b904-fa946b18d315) 

### 4.5. Países com Mais Casos Registrados por Habitantes

O gráfico criado proporciona uma representação clara dos dez países que notificaram os maiores números de casos de COVID-19 por habitante. Essas dez nações respondem por mais de 60% dos registros de indivíduos infectados pelo coronavírus.

![dez países com mais casos por habitantes](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/739afe53-eb03-4adc-9ff5-506d3b731f30)

Além disso, foi gerado um gráfico apresentando os dez países com os maiores registros por  habitantes, utilizando a variável total_cases_per_million. Comparar os países por essa métrica possibilita uma análise mais equitativa e contextualizada da disseminação da COVID-19. Essa abordagem leva em consideração o tamanho da população de cada país, permitindo uma comparação mais precisa dos casos de COVID-19.

Essa metodologia ajuda a identificar quais países estão lidando proporcionalmente com um maior número de casos, independentemente do tamanho absoluto da população. Além disso, auxilia na formulação de estratégias de resposta e na alocação mais eficiente de recursos de saúde. 

### 4.6. Evolução dos Casos Registrados da COVID-19 no Mundo****

A observação da evolução dos casos registrados da COVID-19 em escala global revela a trajetória dessa pandemia que impactou profundamente o mundo. Nesse contexto, a variável new_cases foi utilizada para analisar o registro diário ao longo dos anos.

No gráfico abaixo, é perceptível que ocorreram picos no início e no final de 2022. Diversas razões podem explicar esse aumento significativo no contágio no início desse ano:

**1.** Surgimento de novas variantes do vírus: As variantes Delta e Ômicron, surgidas em 2021 e 2022, respectivamente, são mais contagiosas do que as variantes anteriores do SARS-CoV-2, o vírus causador da COVID-19. Essas variantes podem se espalhar mais rapidamente e resultar em mais infecções.
   
**2.** Relaxamento das medidas de controle da pandemia: No início de 2022, muitos países começaram a flexibilizar as medidas de controle da pandemia, como o uso de máscaras, o distanciamento social e as restrições de viagem. Isso pode ter contribuído para o aumento da transmissão do vírus.

**3.** Baixa taxa de vacinação em alguns países: Alguns países ainda mantinham uma taxa de vacinação contra a COVID-19 relativamente baixa, deixando as pessoas mais vulneráveis à infecção e a formas mais graves da doença.

Em relação ao final de 2022, a China experimentou um pico de casos de COVID-19, com mais de 7 milhões de novos casos registrados diariamente. A China foi um dos últimos países a ser atingido pela variante Ômicron e enfrentou desafios para conter essa variante na população.

![evolução dos casos de covid19](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/ebaa6a71-e5f4-489a-a85a-8d3d922379d0) 

### 4.7. Evolução dos Óbitos devido à COVID-19 no Mundo

O gráfico evidencia um rápido aumento no número de óbitos no início da pandemia, atingindo um pico de mais de 20 mil mortes por dia em janeiro de 2021. A partir desse ponto, observou-se uma diminuição nos registros diários de óbitos, embora tenham permanecido em um patamar elevado. Somente após quase metade de 2022 é que o número diário de óbitos pela COVID-19 começou a diminuir consideravelmente.

Até o momento, aproximadamente 7 milhões de vidas foram perdidas devido à COVID-19 em todo o mundo.

![rigistro diário de óbitos](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/572258c8-2116-4a7e-b2c9-ec02b44bed0f) 

# 5. Análise de Casos e Óbitos no Brasil

A pandemia da COVID-19 teve um impacto expressivo no Brasil, afetando profundamente a saúde pública, a economia e a sociedade como um todo. A chegada da pandemia ao território brasileiro ocorreu em março de 2020, e desde então, o país contabiliza mais de 37 milhões de casos e ultrapassa a marca de 700 mil mortes pela doença. 

### 5.1. Identificação do Primeiro Caso e Primeira Morte

![primeiro caso brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/d574c524-bc05-4862-8e84-e27c766c57e1)

A primeira morte foi identificada cerca de 20 dias após o primeiro caso de COVID-19, quando 291 casos já haviam sido registrados no país.

![primeira morte brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/faad17a4-8694-44c3-a34b-22b4f77adf26)

### 5.2. Valores Estatísticos

**Média e Desvio Padrão:**

A média diária de novos casos de COVID-19 no Brasil foi de aproximadamente 28 mil, com uma considerável variação diária evidenciada pelo desvio padrão superior a 33 mil. Isso sugere momentos de picos significativos de incidência, bem como períodos com menor número de casos.
A média diária de óbitos por COVID-19 no país foi de cerca de 530, com uma variação expressiva indicada pelo desvio padrão de mais de 700 mortes por dia. Essa variação ressalta a ocorrência de períodos com aumento significativo no número de mortes.

**Picos de Casos e Óbitos:**

Os valores máximos registrados, aproximadamente 300 mil novos casos e mais de 4.000 novas mortes, indicam picos extremos em momentos específicos da pandemia no Brasil. Esses picos podem estar associados a surtos agudos da doença, exercendo pressão sobre o sistema de saúde e as medidas de controle (verificado abaixo).

**Média e Mediana:**

Observa-se uma notável discrepância entre a mediana e a média no resumo estatístico para ambas as variáveis. Essa diferença sugere a presença de outliers, ou seja, valores atípicos no conjunto de dados. Esses dados incomuns podem representar picos significativos de incidência de COVID-19 em determinados períodos. Apesar dessa variação acentuada, tanto a mediana quanto a média indicam que o Brasil enfrentou elevados números de novos casos e novas mortes registradas ao longo do tempo.

![valores estatísticos brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/c10f10c4-373d-4abc-8c1d-cb6064e136fb)

### 5.3. Quantidade Total de Casos e Óbitos de COVID-19 no Brasil entre 2020 e 2023

A pandemia deixou um impacto marcante na saúde pública brasileira, com mais de 700.000 mortes e mais de 37 milhões de casos registrados.

O ano de 2020 testemunhou um volume expressivo de casos e óbitos, marcando o início do impacto da doença. No entanto, 2021 se destacou como o ano mais fatal, registrando o dobro de casos e óbitos em comparação com o período anual anterior. Essa escalada pode ser atribuída à disseminação acelerada da variante Delta do vírus.

Ao longo de 2022, embora os casos identificados tenham se mantido semelhantes aos números de 2021, houve uma queda no total de óbitos. Essa redução pode ser creditada ao aumento da cobertura vacinal e à implementação de medidas de saúde pública mais rigorosas.

Em 2023, a OMS declarou o fim da Emergência de Saúde Pública de Importância Internacional relacionada à COVID-19. Nesse mesmo ano, observou-se uma significativa diminuição tanto no número de mortes quanto de casos. Apesar desse cenário, é crucial manter a vigilância e precaução diante da evolução contínua da situação.

![mortes e casos por ano brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/77912734-ab1c-4c64-8756-515ea6dec513) 

### 5.4. Evolução dos Casos Registrados da COVID-19 no Brasil

Ao analisar a trajetória da COVID-19 no Brasil, podemos observar como a disseminação da doença se desenvolveu ao longo do tempo.

O gráfico ilustra que o número de casos de COVID-19 no Brasil teve um aumento rápido no início da pandemia, atingindo um pico de mais de 290.000 novos casos registrados no início de 2022.

Além disso, o gráfico destaca a considerável variabilidade no número de casos de COVID-19 no Brasil. Existem dias com um alto número de casos e dias com uma baixa incidência. Essa variabilidade pode ser atribuída a diversos fatores, como a introdução de novas variantes do vírus, alterações nas medidas de saúde pública e mudanças no comportamento da população.

![evolução de casos no brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/06cd71b6-9600-404a-80ba-ab33cd74955b)

### 5.5. Evolução dos Óbitos devido à COVID-19 no Brasil

O gráfico evidencia que o número de mortes causadas pela COVID-19 no Brasil teve um aumento rápido no início da pandemia, alcançando um pico de mais de 4.000 óbitos em um único dia durante o primeiro semestre de 2021. A despeito de ter permanecido em níveis elevados, a quantidade de mortes começou a declinar após o segundo semestre de 2021.

![evolução de óbitos no brasil](https://github.com/mariacdev/Projeto-Covid-19/assets/134116444/3069994c-76d6-43b5-b0e9-c97c61541341)

# 6. Conclusão

A pandemia global da COVID-19 foi um evento devastador que resultou em milhões de mortes e casos em todo o mundo. Essa crise sanitária teve repercussões significativas na economia global, culminando no fechamento de empresas, perda de empregos e aumento da pobreza em várias partes do planeta. Além disso, impactou negativamente a vida social das pessoas, levando ao isolamento, ansiedade e depressão.

Este projeto utilizou um conjunto de dados do Our World in Data, contendo informações sobre casos e óbitos por COVID-19 em todo o mundo. A análise dos dados revelou:

- As dez nações com os maiores números de casos totalizaram mais de 60% dos registros globais de infectados pelo coronavírus.
- Nos EUA, mais de um milhão de vidas foram perdidas para a COVID-19.
- O ano de 2021 foi o mais fatal em relação à pandemia.
- O Brasil também enfrentou um cenário alarmante de casos e óbitos devido à COVID-19.
- A subnotificação de mortes causadas pela doença pode ter ocorrido devido à complexidade na obtenção precisa dos números.

A análise foi viabilizada pela qualidade e confiabilidade dos dados fornecidos pelo Our World in Data. O dataset oferece diversas informações para uma compreensão mais abrangente do impacto da COVID-19. É possível, por exemplo, realizar uma análise detalhada da vacinação e suas relações com casos e óbitos, além de ampliar as comparações entre países e continentes para examinar diferentes estratégias de controle e suas consequências.

Por fim, é crucial destacar que cada número representa uma história, uma família e um ente querido perdido para esse vírus implacável. Essa realidade tangível destaca como a COVID-19 transcendeu fronteiras e afetou a vida de inúmeras pessoas em todo o mundo.

