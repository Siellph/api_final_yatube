## Учебный проект API для сервиса блогов YATUBE
API для сервиса блогов Yatube через который можно оставлять и просматривать публикации.
Подписываться на других пользователей.
Получать:
записи групп
информацию об авторе
детальную информацию о посте

## Установка
На локальном ПК:
1. создать виртуальное окружение и активировать его
[python -m venv venv]
[source venv/scripts/activate]
2. установить все зависимости
[pip install -r requirements.txt]
3. произвести миграцию БД
[python manage.py migrate]
4. запустить сервер
[python manage.py migrate]

## Примеры запросов к API
Получить все записи
[GET] http://127.0.0.1:8000/api/v1/posts/
Results
```json
{
"id": 0,
"author": "string",
"text": "string",
"pub_date": "2021-10-14T20:41:29.648Z",
"image": "string",
"group": 0
}
```
Создать запись
[POST] http://127.0.0.1:8000/api/v1/posts/
Body
```json
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
Response
200:
```json
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
400:
```json
{
  "text": [
    "Обязательное поле."
    ]
}
```
401:
```json
{
  "detail": "Учетные данные не были предоставлены."
}
```
