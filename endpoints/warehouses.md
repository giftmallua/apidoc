# [GET] /warehouses
## Description: 
Отображает отделения доступные для доставки
## GET parameters:
- `page` - страница (по умолчанию 1)
- `perPage` - кол-во отделений в одном ответе (по умолчанию 100)
## POST parameters:
none
## RESPONSE
- `page`: страница 
- `requested_amount`: максимальное кол-во отделений в ответе
- `get`: полученное кол-во отделений
- `total_amount`: всего доступных отделений
- `items`: Массив элементов
  - `entity`: NPWarehouse
  - `id`: идентификатор отделения
  - `description`: название на украинком 
  - `descriptionRu`: название на русском
  - `cityId`: идентификатор города
## EXAMPLE
#### GET /warehouses?page=65&perPage=100

#### Response
```json
{
"page": "65",
"requested_amount": 100,
"get": 8,
"total_amount": 6408,
"items": {
  "0": {
    "entity": "NPWarehouse",
    "id": 5761,
    "description": "Пункт приймання-видачі (до 30 кг): вул. Бикова, 1/2",
    "descriptionRu": "Пункт приема-выдачи (до 30 кг), ул. Быкова, 1/2",
    "cityId": 4385
  },
  ...
}
```
