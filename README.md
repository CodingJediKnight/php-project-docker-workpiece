## XDEBUG
### Установка
* Прописать нужные env переменные

```bash
XDEBUG_ENABLE=true
XDEBUG_MODE=debug
PHP_IDE_SERVER_NAME=Docker
```

### Настройка IDE (PhpStorm)
* `Preferences => Build, Execution, Deployment => Docker` - настройка docker. Для Mac и Linux локально через сокет.
* `Preferences => PHP => Servers` - Создаем сервер на `+`. `Name` = название сервера из переменной `PHP_IDE_SERVER_NAME`. `Host` = `_`. Прописать верный маппинг от локальной корневой папки до папки проекта внутри контейнер.
* `Preferences => PHP => CLI Interpreters` - Добавляем `From Docker`. `Server` = созданный сервер ранее. `Image` = выбираем контейнер с проектом. Должно уже в окне создания подхватиться `php` и `xdebug`. После создания зайти в 'папку' напротив `Docker Container`. Там нужно указать актуальную сеть в `Network mode`. Актуальную найти в `docker network ls`.
* `Preferences => PHP => Debug` - Порт 9003
* `Preferences => PHP => Test Frameworks => PHPUnit by Remote Interpreters` - Выбрать созданный от докера Interpreter.
