# [GET] /dictionary
## Description: 
Словарь всех значений, которые отображаются или передаются в цифровом виде
## GET parameters:
none
## POST parameters:
none
## RESPONSE
- `{entityName}.{field}`: массив значений конкретного свойства 
  - `id`: `value`: ключ - идентификатор, значение - описание
## EXAMPLE
#### GET /dictionary

#### Response
```json
{
  "order.status": {
    "0": "STATUS_OPEN",
    "1": "STATUS_CONFIRMED",
    "2": "STATUS_PAID",
    "3": "STATUS_COMPLETED",
    "4": "STATUS_CANCELLED",
  },
  "order.paymentStatus": {
    "0": "PAYMENT_STATUS_PREPARE",
    "1": "PAYMENT_STATUS_WAITING",
    "2": "PAYMENT_STATUS_PAID",
    "3": "PAYMENT_STATUS_NOT_PAID_ERROR",
    "4": "PAYMENT_STATUS_NOT_PAID_CANCEL",
    "22": "PAYMENT_STATUS_PAID_LATER"
  },
  "order.deliveryStatus": {
    "0": "DELIVERY_STATUS_PREPARE",
    "1": "DELIVERY_STATUS_CANCEL",
    "2": "DELIVERY_STATUS_WAITING",
    "3": "DELIVERY_STATUS_IN_PROGRESS",
    "4": "DELIVERY_STATUS_DELIVERED",
    "5": "DELIVERY_STATUS_SAFE_IN_WAREHOUSE",
    "6": "DELIVERY_STATUS_CANCEL_RECEIVER",
    "9": "DELIVERY_STATUS_DONE",
    "10": "DELIVERY_STATUS_ERROR",
    "55": "DELIVERY_STATUS_CANCEL_WAREHOUSE"
  },
  "order.deliveryType": {
    "2": "SMS",
    "3": "EMAIL",
    "6": "NOVAPOSHTA_ADDRESS",
    "7": "NOVAPOSHTA_WAREHOUSE"
  },
  "order.paymentType": {
    "0": "payment_type.cash",
    "1": "LiqPay",
    "5": "Platon",
    "6": "payment_type.clearing_settlement",
    "7": "Portmone",
    "8": "WayForPay"
  }
}
```
