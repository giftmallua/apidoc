# [GET] /manager/users
## Description: 
Отображает всех пользователей, доступные в програме лояльности
## GET parameters:
- `id` - фильтрует пользователей по id
- `email` - фильтрует пользователей по email
- `fullName` - фильтрует по имени, фамилии, отчеству (можно как 1 значение, так и все 3 через пробел)
- `activated` - фильтрует пользователей по активен(1) или нет(0) 
- `page` - (default - 1) номер страницы
- `number` - (default - 20) кол-во элементов на странице

## POST parameters:
none
## RESPONSE
- `page`: Текущая страница
- `amount`: Элементов в поле data
- `total_page_count`: Всего страниц
- `total_items_count`: Всего найдено пользователей
- `data`: Массив пользователей
  - `id`: идентификатор пользователя
  - `source`: источник регистрации
  - `tag`: Теги через запятую
  - `email`: эл. почта
  - `full_name`: Фамилия Имя Отчество через пробел
  - `balance`: баланс пользователя, в скобках активный баланс готовый к выводу

## EXAMPLE
#### GET /balance

#### Response
```json
{
    "page": 1,
    "columns": {
        "id": "ID",
        "source": "Источник",
        "tag": "Тег",
        "email": "Email",
        "full_name": "Полное имя",
        "balance": "Баллы"
    },
    "amount": 20,
    "total_page_count": 2,
    "total_items_count": 28,
    "data": [
        {
            "id": 62423,
            "source": "Импорт",
            "tag": "Фармацевт, Менеджер",
            "email": "username@email.com",
            "full_name": "Фамилия Имя Отчество",
            "balance": "950 (950)"
        },
        ...
    ]
}
```
