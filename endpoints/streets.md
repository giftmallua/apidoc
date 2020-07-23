# [GET] /streets
## Description: 
Отображает улицы городов доступных для доставки (НП)
## GET parameters:
- `page` - страница (по умолчанию 1)
- `perPage` - кол-во улиц в одном ответе (по умолчанию 100)
## POST parameters:
none
## RESPONSE
- `page`: страница 
- `requested_amount`: максимальное кол-во улиц в ответе
- `get`: полученное кол-во улиц
- `total_amount`: всего улиц
- `items`: Массив элементов
  - `entity`: NPStreet
  - `id`: идентификатор улицы
  - `description`: название на украинком
  - `cityId`: идентификатор города
## EXAMPLE
#### GET /streets?page=1050&perPage=100

#### Response
```json
{
"page": "1050",
"requested_amount": 100,
"get": 58,
"total_amount": 104958,
"items": {
  "0": {
    "entity": "NPStreet",
    "id": 101184,
    "description": "Богдана Хмельницького",
    "cityId": 3822
  },
  ...
}
```
