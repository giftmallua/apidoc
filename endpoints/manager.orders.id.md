# [GET] /manager/orders/{user_id}
## Description: 
Отображает все заказы пользователя
## GET parameters:
- `page` - (default - 1) номер страницы
- `perPage` - (default - 5) кол-во элементов на странице

## POST parameters:
none
## RESPONSE
- `page`: Текущая страница
- `amount`: Элементов в поле data
- `total_page_count`: Всего страниц
- `total_items_count`: Всего найдено заказов
- `data`: Массив заказов
  - `id`: идентификатор заказа
  - `date`: дата создания
  - `sum`: сумма
  - `products`: Список купленных сертификатов через запятую.
Детальнее о заказе можно узнать [тут](endpoints/orders.md)

## EXAMPLE
#### GET /balance

#### Response
```json
{
    "page": 1,
    "amount": 0,
    "total_page_count": 0,
    "total_items_count": 0,
    "data": []
}
```
