# [GET] /balance
## Description: 
Отображает текущий баланс на аккаунте
## GET parameters:
none
## POST parameters:
none
## RESPONSE
- `balance`: Баланс вашего аккаунта,
- `expire`: Дата, до которой действует баланс (5 лет от даты пополнения),
- `orders`: Количество заказов/пополнений
## EXAMPLE
#### GET /balance

#### Response
```json
{
  "balance": 161737,
  "expire": "2025-06-30T00:00:00",
  "orders": 1
}
```
