# Nginx для AngularDart

## Назначение

Осуществляет редирект всех запросов к серверу на index.html, кроме запросов на получение ресурсов (скриптов, картинок и т.п), что необходимо для корректной работы AngularDart-приложения, так как стандартный `webdev serve` не позволяет переходить по произвольному пути в приложении.

Предназначен исключительно для процесса разработки, так как отключает кэширование.

## Что необходимо для запуска

Должны быть установлены [`docker`](https://docs.docker.com/) и [`docker-compose`](https://docs.docker.com/compose/install/)

## Использование

1. Клонировать этот репозиторий в какой-нибудь каталог, например, `nginx-angular`
2. Запустить AngularDart-приложение командой: `webdev serve --output web:.dart_tool/build/web`
3. Создать линк: `ln -s /path/to/.dart_tool/build/web /path/to/nginx-angular/web`
4. Запустить nginx-сервер: `docker-compose up -d` (для этого необходимо находиться в каталоге `nginx-angular`)
5. Открыть приложение в браузере: `http://localhost:8880`

# Дополнительные настройки

При необходимости можно изменить настройки запуска и конфигурации `nginx` в файлах `docker-compose.yml` и `default.conf` и перезапустить сервер:
```
docker-compose down
docker-compose up -d
```
