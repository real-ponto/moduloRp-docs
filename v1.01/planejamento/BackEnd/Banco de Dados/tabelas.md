
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

## group:
* groupName **string**
* description **string** 

## company:
* companyName **string** 
* contractNumber **string**
* cnpj **string** 
* has one => adress 
* has one => contact

## watch
* numSerial **string**
* port **string** 
* model **string**
* mark **string**
* has one => adress
* has one => contact

# Modulo

## modulorp
* numSerial **string**
* has One  => chip 
* has many => watch 
* has many => item

# Usuarios

## user
* username **string**
* email **string**
* has one => login

## login
* password **string**
* has many => session

## session
* lastActivity **date**
* active **boolean**

## roles
* Name **string**
* description **string**
* has many => resource

## resource
* resource **string**
* route **string**