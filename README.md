# Тестовое задание

Вам необходимо сделать REST сервис для одноразовых секретов наподобие https://onetimesecret.com/

Он должен позволить создать секрет, задать кодовую фразу для его открытия и сгенерировать код, по которому можно прочитать секрет только один раз. UI не нужен, это должен быть JSON Api сервис.
Для написания сервиса можно использовать FastAPI или другой фреймворк.

- Метод `/generate` должен принимать секрет и кодовую фразу и отдавать secret_key по которому этот секрет можно получить.
- Метод `/secrets/{secret_key}` принимает на вход кодовую фразу и отдает секрет.
- Данные сервиса хранятся в базе данных. Можно использовать Postgres или MongoDB.
- Сервис должен использовать Docker и запускаться с помощью `docker-compose up`. Запуск БД также описан в `docker-compose`.

Требования:
- Требований к используемым технологиям нет.
- Сервис асинхронно обрабатывает запросы.
- Секреты и кодовые фразы не хранятся в базе в открытом виде.
- Код должен соответствовать PEP, необходимо использование type hints, к публичным методам должна быть написана документация.
- Написаны тесты (постарайтесь достичь покрытия в 70% и больше). Вы можете использовать pytest или любую другую библиотеку для тестирования
- Сервис должен корректно обрабатывать валидные и невалидные входящие запросы и выдавать соответствующие HTTP статусы

## Дополнительно (по желанию)
- Добавить возможность ограничения количества запросов (напр., 600 в минуту). При превышении лимита, сервер должен возвращать статус «429 Too Man Requests»
- Разместить образ контейнера на Docker Hub для возможности независимой установки на другой машине (все сервисы должны развернуться стандартной командой)