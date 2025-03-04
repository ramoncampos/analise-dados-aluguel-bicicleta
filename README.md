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

## Instructions
1. Comece com o notebook `aluguel_bicicleta_Clean.ipynb`para explorar e limpar os dados de uso do Citi Bike.
2. Execute o script `aluguel_bicicleta_ERD.sql` em [dbdiagram.io](https://dbdiagram.io) para criar o esquema do banco de dados PostgreSQL como `aluguel_bicicleta_ERD.pdf`
3. Execute o script "Creating the Database" e "Creating PostgreSQL Tables" no arquivo `aluguel_bicicleta_Clean.ipynb` para transformar e carregar os dados integrados no banco de dados PostgreSQL.
4. Por fim, execute o script `aluguel_bicicleta_views.sql` para criar views prontas para análise para a equipe de analytics.

## Arquivos Necessários
* ### Dados
	* `newark_airport_2016.csv`: dados meteorológicos do aeroporto de Newark.
	* `JC-2016xx-citibike-tripdata.csv`: 12 arquivos, cada um contendo os dados de um mês de aluguel de bicicletas do Citi Bike de Jersey City.

* ### Dicionário de Dados
	* `citibike.pdf`: detalhes sobre os arquivos de dados do Citi Bike estão disponíveis no site do Citi Bike.
	* `weather.pdf`: detalhes sobre os dados meteorológicos estão disponíveis no site da NOAA (Administração Nacional Oceânica e Atmosférica).

## Observação
Certifique-se de ter os direitos de acesso e credenciais necessários para criar e manipular bancos de dados no PostgreSQL. Atualize os detalhes de conexão e os caminhos dos arquivos conforme necessário nos scripts
