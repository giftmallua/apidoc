# [GET] /filters
## Description: 
Отображает структуру фильтров(категорий заведений)
## GET parameters:
none
## POST parameters:
none
## RESPONSE
- `items` 
  - `filter`: Данные категории
    - `entity`: Filter
    - `id`: идентификатор фильтра
    - `url`: техническое название фильтра, используется в запросах
    - `title`: Человекопонятное название фильтра
    - `category`: можно ли фильтровать заведения по этому параметру (true/false)
  - `values`: фильтра этой категории
    - `[]`: элемент массива, имеющий структуру entity Filter (см выше)
## EXAMPLE
#### GET /filters

#### Response
```json
{
  "items": {
    "0": {
      "filter": {
        "entity": "Filter",
        "id": 3,
        "url": "type",
        "title": "Тип сертификата",
        "category": false
      },
      "values": {
        "0": {
          "entity": "Filter",
          "id": 23,
          "url": "email",
          "title": "Электронный",
          "category": true
        },
        "1": {
          "entity": "Filter",
          "id": 24,
          "url": "plastic",
          "title": "Пластиковый",
          "category": true
        },
        "2": {
          "entity": "Filter",
          "id": 25,
          "url": "sms",
          "title": "SMS",
          "category": true
        }
      }
    },
    ...
  }
}
```
