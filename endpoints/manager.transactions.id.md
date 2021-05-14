# [GET] /manager/transactions/{user_id}
## Description: 
Отображает все транзакции пользователя
## GET parameters:
- `page` - (default - 1) номер страницы
- `perPage` - (default - 5) кол-во элементов на странице

## POST parameters:
none
## RESPONSE
- `page`: Текущая страница
- `amount`: Элементов в поле data
- `total_page_count`: Всего страниц
- `total_items_count`: Всего найдено транзакций
- `data`: Массив транзакций
  - `id`: идентификатор транзакции
  - `date`: дата создания
  - `active`: дата, с какого момента готово в квыводу
  - `sum`: сумма
  - `manager`: email менеджера
  - `cancelled`: отменен да(1)/нет(0)
  - `order`: заказ, на который была потрачена сумма
  - `inactive`: true/false активность баланса для пользователя

## EXAMPLE
#### GET /balance

#### Response
```json
{
    "page": 1,
    "amount": 5,
    "total_page_count": 1,
    "total_items_count": 5,
    "data": [
        {
            "id": 432,
            "date": "09.04.2021 11:08",
            "active": "09.04.2021 11:08",
            "type": "replenishment",
            "sum": "460.00",
            "manager": "user@mail.com",
            "cancelled": false,
            "order": "",
            "inactive": false
        },
        ...
    ]
}
```
