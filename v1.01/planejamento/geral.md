# Versão 1.01 MVP

# Visão Geral

Podemos dividir o projeto em algumas partes lógicas como mostrado a seguir:

![Diagram1](https://i.imgur.com/pMbr527.png "Diagrama geral")

## Composto por:
* Banco de dados
* BackEnd
* Serviço Ping
* Front de Overwiew
* Front de DashBoard e Cadastro


### Banco de dados

O banco de dados escolhido foi o Postegree, porque ele é robusto e relacional. 

Versão:
* postgres:9.6.5-alpine

### BackEnd

No BackEnd iremos trabalhar com o nodejs com o Express pois a velocidade de desenvolvimento é 
elevada proporcionando uma maior fluidez para o projeto. 

Escolhemos o sequalizer como ORM pela facilidade de lidar com as querys do 
banco de dados. 

Decidimos fazer monolito pelo tempo de desenvolvimento e a equipe pequena. 
