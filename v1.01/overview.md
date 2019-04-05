# Versão 1.01 MVP



# Visão Geral

O projeto implica em um software de controle e gestão dos módulos da empresa. 

Podemos dividir o projeto em algumas partes lógicas como mostrado a seguir:

![Diagram1](https://i.imgur.com/pMbr527.png "Diagrama geral")

composto por:
* Banco de dados
* BackEnd
* Serviço Ping
* Front de Overwiew
* Front de DashBoard e Cadastro

# Tabelas De Cadastro

## chip:
* numchip: 10 digitos string **UNIQUE**
* ip: string 
* operadora: Enum [Vivo, Claro, Tim, Oi]

## Empresa:
* Razao social
* Nome fantasia
* Cnpj **UNIQUE**
* has one => Endereço
* has one => ContatoID

## Modulo:
* Numero Serie **UNIQUE**
* has One => chip **UNIQUE**
* has many => relogios **UNIQUE**
* has many => Estoque Itens

## Relogio
* Numero Serie **UNIQUE**
* porta
* modelo
* marca
* has one => Endereço
* has one => ContatoID

## Modem
* Numero Serie
* Marca
* Modelo

## TpLink
* Numero Serie
* versão

## Fonte
* Numero Serie

## user
* username
* email
* has one => login

## login
* login
* password
* has many => session

## session
* lastActivity
* active

## Roles
* Name
* description
* recursosList

## lista descarte
* ItemType 
* Item ID
