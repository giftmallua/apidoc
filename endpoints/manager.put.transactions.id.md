# [PUT] /manager/transactions
## Description: 
Добавляет транзакцию
## GET parameters:
none

## POST parameters:
- `sum` - сумма
- `user` - id пользователя (в Giftmall)
- `activeDate` - дата, с которой баланс будет активный (default - now) формат Y-m-dTH:i:s
- `inactive` - по умолчанию false (активный), true - для неактивного баланса


## RESPONSE
- `status`: Статус true/false
- `id`: идентификатор транзакции в случае статуса true

## EXAMPLE
GET /manager/transactions
```
sum=300&user=13941&activeDate=2021-01-01T00:00:00&inactive=true
```
#### Response
```json
{
   "status": true,
   "id": 123456
}
```
