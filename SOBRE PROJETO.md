# Gestão de Dados de Aluguel de Bicileta

## Introdução 

Trabalhei com um ano de dados de aluguel de bicicletas fornecidos pela Citi Bike e dados meteorológicos da Administração Nacional Oceânica e Atmosférica (NOAA). O objetivo final foi produzir um banco de dados PostgreSQL bem organizado e desenvolver views para facilitar a análise pela equipe de analytics da empresa, a fim de entender os efeitos do clima no aluguel de bicicletas. No processo de desenvolvimento do projeto de Gestão de Dados de Aluguel de Bicicletas, minha abordagem foi orientada por uma combinação de exploração de dados, limpeza, integração e princípios de design de banco de dados.

 
## Preparando os Dados
[Jupyter Notebook](./aluguel_bicicleta_Clean.ipynb)

**Abordagem:**
Utilizando o Jupyter notebook e a biblioteca pandas para Python, concatenei os 12 arquivos de dados (um para cada mês de 2016) em um único dataframe para realizar a exploração inicial e limpeza dos dados de uso do Citi Bike. Minhas observações iniciais identificaram problemas de qualidade nos dados, como dados demográficos de ciclistas ausentes. Embora os dados ausentes representem uma pequena porcentagem do total, ao plotar os dados e observar as distribuições, percebi que esses dados podem não estar ausentes de forma aleatória.
Além disso, investiguei as durações das viagens dos dados de uso do Citi Bike. Havia uma duração máxima de viagem suspeitamente grande de 189 dias. De acordo com o dicionário de dados, as políticas do Citi Bike afirmam que a duração máxima de uma viagem é de 24 horas.

**Tomada de Decisão:**
Dada a natureza real dos conjuntos de dados, optei por manter os dados, mas substituir os valores ausentes por uma categoria "desconhecida", para que a equipe de análise possa investigar mais a fundo e acompanhar o problema. Também criei uma coluna para sinalizar viagens que violam as políticas de empréstimo, o que os analistas podem querer investigar.


## Criando um schema
[Bike Rental Entity Relationship Diagram](./aluguel_bicicleta_ERD.pdf)

**Abordagem:**
Escolhi o PostgreSQL como o banco de dados relacional para armazenar os dados integrados. Durante a limpeza e transformação dos dados, utilizei técnicas de normalização para projetar um esquema de banco de dados bem organizado, garantindo a integridade dos dados. Verifiquei a presença de valores nulos, duplicatas e quaisquer dados repetitivos que pudesse dividir em várias tabelas.

**Tomada de Decisão:**
A decisão de usar o dbdiagram.io foi baseada na simplicidade de usar código SQL para desenhar diagramas de relacionamento entre entidades. Utilizei chaves primárias e chaves estrangeiras para estabelecer relacionamentos e possibilitar consultas eficientes nas tabelas que criei.


## Criando a Base de Dados
[Jupyter Notebook](./aluguel_bicicleta_Clean.ipynb)

**Abordagem:**
Escolhi a biblioteca psycopg2 e desenvolvi um código em Python para carregar os dados limpos e integrados no banco de dados PostgreSQL.

**Tomada de Decisão:**
O psycopg2 foi escolhido por sua capacidade de interagir de forma eficiente com o PostgreSQL, conectar-se ao banco de dados e executar consultas SQL.


## Criando views
[Bike Rental Views](./aluguel_bicicleta_views.sql)

**Abordagem:**
Decidi criar views dentro do banco de dados para garantir que os analistas tenham acesso a dados pré-processados, reduzindo a necessidade de transformações repetitivas. Usei consultas SQL para criar views prontas para análise dentro do banco de dados PostgreSQL.

**Tomada de Decisão:** 
Criei uma view para contagem diária de viagens, que permite aos analistas visualizar os totais de viagens por tipo de cliente para cada dia do ano.
Também criei uma view para dados meteorológicos diários e totais de viagens, para que os analistas possam observar os efeitos do clima no aluguel de bicicletas.
Por fim, uma view chamada "late returns" foi criada para que os analistas investiguem as viagens que violam a política de empréstimo do Citi Bike.


## Conclusion
Minha abordagem ao processo de desenvolvimento teve como objetivo equilibrar proficiência técnica e uma abordagem cuidadosa no tratamento dos dados. Tomei decisões sobre as ferramentas, a linguagem a ser usada e o design do esquema do banco de dados, com o objetivo final de fornecer uma solução robusta e eficiente para a equipe de análise, permitindo extrair insights úteis dos dados de aluguel de bicicletas e clima. A natureza iterativa do processo permitiu aprendizado e ajustes, com base em novos insights e desafios encontrados ao longo do caminho.
