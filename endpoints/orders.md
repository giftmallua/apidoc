# [GET] /orders
## Description: 
Отображает список заказов (корпоративных/пополнений баланса и заказов API)
## GET parameters:
none
## POST parameters:
none
## RESPONSE
- `orders` - список заказов 
  - `entity`: Order - отображается структура [GET /orders/{id}](/endpoints/orders.id.md) без элементов заказа
- `dictionary`: выводится структура [dictionary](/endpoints/dictionary.md) со свойствами, которые есть в теле ответа
## EXAMPLE
#### GET /orders

#### Response
```json
{
  "orders": {
    "0": {
      "entity": "Order",
      "id": 93382,
      "status": 3,
      "paymentStatus": 22,
      "deliveryStatus": 10,
      "deliveryType": 3,
      "sum": "104577.50",
      "sumDiscounted": "104577.50",
      "createDate": "2019-12-23T17:20:00",
      "invoice": null
    },
    ...
  },
  "dictionary": {...}
}
```
