# [GET] /catalogs
## Description: 
Отображает список всех доступных заведений
## GET parameters:
- `params` - детальнее в [GET /catalogs/{id}](/endpoints/catalogs.id.md)
- `page` - страница (по умолчанию 1)
- `perPage` - кол-во заведений в одном ответе (по умолчанию 10)
-  `filters` - набор фильтров ([url фильтра](/endpoints/filters.md)) через запятую в формате `filters=category={url1},{url2}`
## POST parameters:
none
## RESPONSE
- `page`: страница 
- `requested_amount`: максимальное кол-во заведений в ответе
- `get`: полученное кол-во заведений
- `total_amount`: всего заведений
- `items`: Массив элементов
  - `entity`: Catalog
    - структуру  Entity Catalog можно найти в [GET /catalogs/{id}](/endpoints/catalogs.id.md)

## EXAMPLE
#### GET /catalogs?filters=category=produkty_pitaniya,50

#### Response
```json
{
  "page": 1,
  "requested_amount": 10,
  "get": 3,
  "total_amount": 3,
  "items": {
    "0": {
      "entity": "Catalog",
      "id": 9,
      "title": "Novus",
      "fixPrices": {
        "физ": {
          "18": 50,
          "19": 100,
          "20": 200,
          "21": 500,
          "22": 1000
        },
        "ел": {
          "4": 50,
          "18": 100,
          "19": 200,
          "20": 500,
          "21": 1000
        }
      },
      "services": {},
      "picture": "giftmall.com.ua/...jpeg",
      "minPrice": 50,
      "maxPrice": 500000,
      "allowSms": false,
      "allowMail": true,
      "allowPhysical": false
      },
      ...
    }
}
```
