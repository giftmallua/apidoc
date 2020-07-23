# [GET] /cities
## Description: 
Отображает населенные пункты, в которые доставляет перевозчик (НП)
## GET parameters:
- `page` - страница (по умолчанию 1)
- `perPage` - кол-во улиц в одном ответе (по умолчанию 100)
## POST parameters:
none
## RESPONSE
- `page`: страница 
- `requested_amount`: максимальное кол-во населенных пунктов в ответе
- `get`: полученное кол-во населенных пунктов
- `total_amount`: всего населенных пунктов
- `items`: Массив элементов
  - `entity`: NPCity
  - `id`: идентификатор населенного пункта
  - `description`: название на украинком
  - `descriptionRu`: название на русском
## EXAMPLE
#### GET /cities?page=44&perPage=100

#### Response
```json
{
"page": "44",
"requested_amount": 100,
"get": 93,
"total_amount": 4393,
"items": {
  "0": {
    "entity": "NPCity",
    "id": 4301,
    "description": "Юрківка (Черкаська обл.)",
    "descriptionRu": "Юрковка (Черкасская обл.)"
  },
...
}
```
