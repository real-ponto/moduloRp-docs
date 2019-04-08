
# Tabelas De Cadastro

# Chip

## chip:
* numChip: **string**
* ip: **string**
* lot **string** 
* status: **ENUM** [
  stock, 
  loanToEmployee, 
  test, 
  reserved, 
  inModule,
  dead
] 

* has one => chipOut 
* has one => chipProvider
* has many => chipEvent 

## chipProvider:
* mobileProvider **string**

## chipOut:
* employeeName **string**
* dateLoan: **date**
* dateReturned: **date**
* belongTo => chip

## chipEvent:
* date: **date**
* event: **string**
* belongTo => chip

# Outros Itens(tplink, modem, fonte, etc):

## item:
* numSerial **string**
* mark **string**
* lot **string**
* status: **ENUM** [
  stock,  
  loanToEmployee, 
  test, 
  reserved, 
  inModule,
  dead
]
* has one => itemType 
* has one => itemModel 

## itemType:
* type **string** 
* isRequired **boolean**

## itemModel:
* mark **string** 
* model **string** 
* seller **string**

## itemOut:
* employeeName **string**
* dateLoan: **date**
* dateReturned: **date**

## itemEvent:
* date: **date**
* event: **string** 
* belongTo => item 

# Relogios

## company:
* Razao social **UNIQUE** 
* Nome fantasia  
* Cnpj **UNIQUE** 
* has one => Endereço 
* has one => Contato 

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
