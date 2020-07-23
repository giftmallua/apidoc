# [GET] /orders/{id}
## Description: 
Отображает детальную информацию о заказе
## GET parameters:
none
## POST parameters:
none
## RESPONSE
- `entity`: Order 
- `id`: идентификатор заказа
- `status`: идентификатор статуса заказа (детальнее [GET /dictionary](/endpoints/dictionary.md))
- `paymentStatus`: идентификатор статуса оплаты (детальнее [GET /dictionary](/endpoints/dictionary.md))
- `deliveryStatus`: идентификтаор статуса доставки (детальнее [GET /dictionary](/endpoints/dictionary.md))
- `deliveryType`: идентификатор типа доставки (детальнее [GET /dictionary](/endpoints/dictionary.md))
- `sum`: сумма по заказу
- `sumDiscounted`: сумма доплаты
- `createDate`: дата создания
- `invoice`: ссылка на счет (только для пополнения баланса)
- `items`: массив элементов заказа
  - `entity`: OrderItem
  - `id`: идентификатор элемента заказа
  - `quantity`: кол-во сертификатов
  - `catalog`: выводится структура [entity Catalog](/endpoints/catalog.id.md), без доп. полей (см [response](#Response))
  - `price`: номинал сертификата
  - `certificates`: массив сертификатов (могут быть 2х типов: CertificatePartner, Certificate)
    - `entity`: CertificatePartner/Certificate
    - `id`: идентификатор сертификата
    - `codePartner`(только CertificatePartner): дополнительный код или пин код, если это предусмотрено самой сетью (может быть null)
    - `code`: секретный код, код для использования в магазине (если есть codePartner, может быть не основным кодом, зависит от сети)
    - `nominal`: номинал сертификата
    - `expireDate`: дата действия сертификата
    - `catalog`: выводится структура [entity Catalog](/endpoints/catalog.id.md), без доп полей (см [response](#Response))
    - `image`: ссылка на картинку сертификата, со всеми нужными данными
- `dictionary`: выводится структура [dictionary](/endpoints/dictionary.md), со свойствами, которые есть в теле ответа
## EXAMPLE
#### GET /orders/122222

#### Response
```json
{
   "entity":"Order",
   "id":122222,
   "status":3,
   "paymentStatus":2,
   "deliveryStatus":0,
   "deliveryType":3,
   "sum":"291.00",
   "sumDiscounted":"0.00",
   "createDate":"2020-07-22T17:35:54",
   "invoice":null,
   "items":{
      "0":{
         "entity":"OrderItem",
         "id":177777,
         "quantity":1,
         "catalog":{
              "entity": "Catalog",
              "id": 281,
              "title": "Yakaboo",
              "fixPrices": {
                "физ": {},
                "ел": {
                  "2": 200,
                  "3": 300
                }
              },
              "services": {},
              "picture": "giftmall.com.ua/...jpeg",
              "minPrice": 200,
              "maxPrice": 500000,
              "allowSms": false,
              "allowMail": true,
              "allowPhysical": false
         },
         "price":300,
         "certificates":{
            "0":{
               "entity":"CertificatePartner",
               "codePartner":null,
               "id":1286666,
               "code":"*******",
               "nominal":300,
               "expireDate":"2021-07-31T00:00:00",
               "catalog":{
                  "entity": "Catalog",
                  "id": 281,
                  "title": "Yakaboo",
                  "fixPrices": {
                    "физ": {},
                    "ел": {
                      "2": 200,
                      "3": 300
                    }
                  },
                  "services": {},
                  "picture": "giftmall.com.ua/...jpeg",
                  "minPrice": 200,
                  "maxPrice": 500000,
                  "allowSms": false,
                  "allowMail": true,
                  "allowPhysical": false
               },
               "image":"https://giftmall.com.ua/...png"
            }
         }
      }
   },
   "dictionary":{
      "order.status":{
         ...
      },
      "order.paymentStatus":{
         ...
      },
      "order.deliveryStatus":{
         ...
      },
      "order.deliveryType":{
         ...
      }
   }
}
```
