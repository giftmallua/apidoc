# [PUT] /manager/transactions
## Description: 
Добавляет транзакцию
## GET parameters:
- `sum` - сумма
- `user` - фильтрует пользователей по email
- `active` - дата, с которой баланс будет активный (default - now)

## POST parameters:
none
## RESPONSE
- `status`: Статус success/error
- `id`: идентификатор транзакции в случае статуса success
