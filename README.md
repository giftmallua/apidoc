# Giftmall API

Для работы с API вам потребуется токен и аккаунт. 
Запрос имеет структуру:

- RU - `//{account}.giftmall.com.ua/api/v1/{endpoint}?token={token}&{endPointParams}`
- UA - `//{account}.giftmall.com.ua/uk/api/v1/{endpoint}?token={token}&{endPointParams}`
- EN - `//{account}.giftmall.com.ua/en/api/v1/{endpoint}?token={token}&{endPointParams}`

  - account - поддомен/имя аккаунта, уникальная ссылка для идентификации
  - endpoint - url запроса (все endpoints можно найти ниже)
  - token - код для аутентификации аккаунта (новый токен выдается по запросу)
  - endPointParams - дополнительные GET параметры, у каждого endpoint есть свой список доступных параметров

Обратите внимание, что на тестовом сервере используется http соединение, а на основном сайте https

## Endpoints

* [Show info](endpoints/balance.md) : `GET /balance` - отображает текущий баланс на аккаунте
* [Show info](endpoints/filters.md) : `GET /filters` - отображает дерево доступных фильтров (категории, номиналы)
* [Show info](endpoints/catalogs.md) : `GET /catalogs` - отображает все доступные для покупки заведения
* [Show info](endpoints/catalogs.id.md) : `GET /catalogs/{id}` - отображает конкретное заведение, его наличие на складе
* [Show info](endpoints/orders.md) : `GET /orders` - отображает все заказы, сделанные через API или менеджера
* [Show info](endpoints/orders.id.md) : `GET /orders/{order_id}` - отображает конкретный заказ, все его элементы и купленные продукты
* [Show info](endpoints/post.orders.md) : `POST /orders` - метод для оформления заказа
* [Show info](endpoints/post.reserves.md) : `POST /reserves` - метод для резервации нужных продуктов на определенное время
* [Show info](endpoints/cities.md) : `GET /cities` - отображает доступные для доставки города (НП)
* [Show info](endpoints/streets.md) : `GET /streets` - отображает доступные для доставки улицы (НП)
* [Show info](endpoints/warehouses.md) : `GET /warehouses` - отображает доступные для доставки отделения (НП)
* [Show info](endpoints/dictionary.md) : `GET /dictionary` - отображает актуальную БД всех числовых значений, которые требуют расшифровки

## Ошибки
Если, по какой то причине, вы получили в ответ http статус не равен 200, значит запрос был выполен не полностью или проигнорирован
Пример ответа `{"error":{"code":400,"status":103,"message":"deliveryDateTimeEmail - This value is not valid., "}}` 

- status: 101 - не найден токен в запросе
- status: 102 - не валидный токен
- status: 103 - в теле запроса найдена ошибка (ошибки в формате "field - error text, field - error text")
- status: 104 - не найден запрашиваемый объект
- status: 105 - не достаточно баланса для проведения операции
- status: 106 - данные не актуальны (недостаточное количество сертификатов или заведение не доступно)

## Пример простого алгоритмa работы с API
- Перед началом использования рекомендуем сохранить себе структуру [фильтров](endpoints/filters.md), и [заведений](endpoints/catalogs.md)
- Перед оформлением заказа проверяем наличие нужного типа и номинала в [заведении](endpoints/catalogs.id.md)
- Если номинал существует, отправляем запрос на [создание заказа](endpoints/post.orders.md). В ответ вы получите номер заказа, и возможность [проверить информацию по нему](endpoints/orders.id.md). Информация по продуктам(сертификатам) может обновляться до 2х минут, в зависимости от выбранного заведения.

![Block scheme](/1111.png)

