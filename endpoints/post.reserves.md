# [POST] /reserves
## Description: 
Резервирует сертификаты нужного номинала на определенное время
## GET parameters:
none
## POST parameters:
- `catalog` - id заведения
- `service` - id услуги, которую нужно зарезервировать (не обязательно, если указан номинал)
- `nominal` - номинал сертификата, который нужно зарезервировать (не обязательно, если указана услуга)
- `count` - кол-во сертификатов для резерва
-  `type` - тип сертификата (ниже доступные варианты)
  - `физ` - физические сертификаты
  - `ел` - электронные сертификаты (email, sms)
- `time` - время для резерва от 60 до 600 секунд (по умолчанию 120 секунд)
## RESPONSE
- `result`: статус true/false 
## EXAMPLE
#### GET /reserves
#### POST BODY
```json
{
"catalog": 11,
"nominal": 200,
"count":4,
"type": "ел",
"time": 600
}
```

#### Response
```json
{
"result": true
}
```
