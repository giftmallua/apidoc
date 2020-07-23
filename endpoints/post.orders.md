# [POST] /orders
## Description: 
Оформление заказа
## GET parameters:
none
## POST parameters:
Обязательные поля
- `items`: массив элементов заказа
  - `quantity`: кол-во сертификатов
  - `price`: номинал сертификата, если нужно купить номинальный сертификат
  - `service`: id услуги заведения, price в таком случае указывать не обязательно
  - `deliveryType`: тип сертификата (1 - физическая карта, 2 - sms сертификат(код без картинки), 3 - эл. сертификат (картинка))
  - `catalog`: идентификатор заведения
- `phone`: телефон компании
- `paymentType`: способ оплаты, детальнее в [GET /dictionary](/endpoints/dictionary.md), если вы работаете по предоплате, способ оплаты = 8 (WayForPay)
- `cityCartReceiver`: id города, детальнее в [GET /cities](/endpoints/cities.md)

Дополнительные поля при оформлении эл. сертификата (deliveryType = 3)
- `emailReceiver`: email, на который будет отправлен сертификат (если отправкой занимаетесь вы, укажите example@example.example)
- `firstNameEmailReceiver`: имя получателя (используется при отправке письма)
- `deliveryDateTimeEmail`: время отправки сертификата

Дополнительные поля при оформлении sms сертификата (deliveryType = 2)
- `phoneReceiver`: телефон, на который будет отправлен код сертификата (если отправкой занимаетесь вы, укажите +380111111111)
- `firstNamePhoneReceiver`: имя получателя (используется при отправке sms)
- `deliveryDateTimeSms`: время отправки сертификата

Дополнительные поля при оформлении физических сертификатов
- `typeDeliveryCart`: способ доставки физ. сертификата, свойство order.deliveryType в [GET /dictionary](/endpoints/dictionary.md)
- `firstNameCartReceiver`: имя получателя для службы доставки
- `lastNameCartReceiver`: фамилия получателя для службы доставки
- `phoneCartReceiver`: телефон получателя для службы доставки
- `warehouseCartReceiver`: id отделения для доставки, детальнее в [GET /warehouses](/endpoints/warehouses.md)
- `houseCartReceiver`: номер дома для адресной доставки
- `streetCartReceiver`: id улицы для адресной доставки, детальнее в [GET /streets](/endpoints/streets.md)
- `deliveryDatePhys`: время отправки сертификата

## RESPONSE
- `success`: массив заказов, которые успешно прошли оплату(заказы с постоплатой считаются успешными по умолчанию). Структура заказов, как и в [GET /orders](/endpoints/orders.md)
- `process`: массив заказов, которые ожидают оплату. Структура заказов, как и в [GET /orders](/endpoints/orders.md)
- `errors`: массив заказов, которые не прошли отплату. Структура заказов, как и в [GET /orders](/endpoints/orders.md)
## EXAMPLE
#### GET /orders
#### POST BODY
```json
{
   "items":[
      {
         "quantity":1,
         "price":501,
         "deliveryType":3,
         "catalog":1
      }
   ],
   "phone":"+380111111111",
   "paymentType":8,
   "phoneReceiver":"+380111111111",
   "firstNamePhoneReceiver":"test company",
   "deliveryDateTimeSms":"2020-07-16T12:33:22",
   "cityCartReceiver":1
}
```

#### Response
```json
{
   "success":{
      "0":{
         "entity":"Order",
         "id":107111,
         "status":3,
         "paymentStatus":2,
         "deliveryStatus":0,
         "deliveryType":3,
         "sum":526,
         "sumDiscounted":0,
         "createDate":"2020-07-17T08:16:12",
         "invoice":null
      }
   },
   "process":{

   },
   "errors":{

   },
   "dictionary":{...}
}
```
