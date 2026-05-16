## Лабораторная работа №28. Веб-сервер на C#: список любимых игр с полным управлением


## Описание проекта

Проект представляет собой простое веб-API на ASP.NET Core для управления списком любимых видеоигр. Данные хранятся в памяти сервера. API поддерживает получение списка игр, получение одной игры по ID, добавление новой игры, обновление существующей и удаление игры.

## Инструкция по запуску 
```bash
    cd GamesApi && dotnet run
```

## Таблица всех маршрутов

| Метод   | Маршрут                   | Описание                   | Статусы               |
|---------|---------------------------|----------------------------|-----------------------|
| GET     | /api/games                | Получить все игры          | 200                   |
| GET     | /api/games/{id}           | Получить игру по id        | 200 / 404             |
| POST    | /api/games                | Добавить игру              | 201                   |
| PUT     | /api/games/{id}           | Обновить игру (полностью)  | 200 / 404             |
| DELETE  | /api/games/{id}           | Удалить игру               | 204 / 404             |

## Примеры curl-команд для каждого маршрута

GET /api/games – получить все игры
```bash
    curl http://localhost:5000/api/games
```
GET /api/games/{id} – получить одну игру
```bash
    curl http://localhost:5000/api/games/1
````
POST /api/games – добавить новую игру
```bash
    curl -X POST http://localhost:5000/api/games \
      -H "Content-Type: application/json" \
      -d "{\"title\": \"Stardew Valley\", \"genre\": \"Simulation\", \"releaseYear\": 2016}"
```
PUT /api/games/{id} – обновить игру
```bash
    curl -X PUT http://localhost:5000/api/games/2 \
      -H "Content-Type: application/json" \
      -d "{\"title\": \"The Witcher 3\", \"genre\": \"RPG\", \"releaseYear\": 2015}"
```
DELETE /api/games/{id} – удалить игру
```bash
    curl -X DELETE http://localhost:5000/api/games/1
```
