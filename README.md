# Análise de Dados de Aluguel de Bicicleta

## Visão Geral do Projeto
Este projeto envolve a exploração, limpeza e integração dos dados de uso do Citi Bike com os dados meteorológicos da NOAA para criar um banco de dados PostgreSQL com views prontas para análise. O objetivo é ajudar uma empresa de aluguel de bicicletas a analisar o impacto das condições climáticas no aluguel de bicicletas.

## Objetivos do Projeto
* Utilizar o Jupyter notebook e o pandas para explorar, limpar e transformar os dados de uso do Citi Bike.
* Projetar e implementar um esquema de banco de dados relacional PostgreSQL para armazenar os dados integrados.
* Desenvolver consultas SQL para criar views prontas para análise no banco de dados.

## Dependencias
* Jupyter Notebook
* Biblioteca pandas para manipulação de dados em Python.
* [dbdiagram.io](https://dbdiagram.io) Uma ferramenta de design de relacionamento de banco de dados.
* Banco de Dados PostgreSQL

## Instruções
1. Comece com o notebook `aluguel_bicicleta_Clean.ipynb`para explorar e limpar os dados de uso do Citi Bike.
2. Execute o script `aluguel_bicicleta_ERD.sql` em [dbdiagram.io](https://dbdiagram.io) para criar o esquema do banco de dados PostgreSQL como `ERD_bicicleta.png`
3. Execute o script "Creating the Database" e "Creating PostgreSQL Tables" no arquivo `aluguel_bicicleta_Clean.ipynb` para transformar e carregar os dados integrados no banco de dados PostgreSQL.
4. Por fim, execute o script `aluguel_bicicleta_views.sql` para criar views prontas para análise para a equipe de analytics.

## Arquivos Necessários
* ### Dados
	* `newark_airport_2016.csv`: dados meteorológicos do aeroporto de Newark.
	* `JC-2016xx-citibike-tripdata.csv`: 12 arquivos, cada um contendo os dados de um mês de aluguel de bicicletas do [Citi Bike](https://citibikenyc.com/system-data) de Jersey City.

* ### Dicionário de Dados
	* `citibike.pdf`: detalhes sobre os arquivos de dados do Citi Bike estão disponíveis no site do [Citi Bike](https://citibikenyc.com/system-data).
	* `weather.pdf`: detalhes sobre os dados meteorológicos estão disponíveis no site da NOAA (Administração Nacional Oceânica e Atmosférica).

* ### Diagrama Entidade Relacionamento
  ![ERD](https://github.com/ramoncampos/analise-dados-aluguel-bicicleta/blob/main/ERD_bicicleta.png?raw=true)

## Observação
Certifique-se de ter os direitos de acesso e credenciais necessários para criar e manipular bancos de dados no PostgreSQL. Atualize os detalhes de conexão e os caminhos dos arquivos conforme necessário nos scripts.

## Principais Insights
- Temperatura influencia diretamente no uso: Em dias com temperatura entre 20°C e 30°C, o número de aluguéis foi em média 35% maior do que em dias muito frios ou quentes.
- Dias chuvosos reduzem o uso significativamente: Quando a precipitação ultrapassa 2mm, a demanda por bicicletas cai em até 40%.
- Horários de pico bem definidos: Os maiores picos de aluguel ocorrem entre 7h-9h e 17h-19h, indicando um forte uso para deslocamento casa-trabalho.
- Fins de semana apresentam um padrão diferente: O aluguel de bicicletas é 20% maior aos sábados e domingos após as 10h, sugerindo uso para lazer e turismo.
