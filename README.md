# DipHost
Базовые образы нам не очень нравится, поэтому тут будет велосипед
* debian -> ubuntu (ибо нефиг)
* версии с 5.2 (update.sh позволит генерировать наборы только начиная с 5.4), более старые версии прийдётся делать копипастой, но так как обновление им врядли грозит...
* может ещё чего по сборке (модули по умолчанию и всё такое)

update.sh require `yum install jq`

Для того что бы всё сработало, под каждый релиз надо создать структуру (где 5.3 номер релиза, без последнего номера версии)
```
5.3
├── alpine
│   └── patches
├── apache
│   └── patches
├── fpm
│   ├── alpine
│   │   └── patches
│   └── patches
├── patches
└── zts
    ├── alpine
    │   └── patches
    └── patches
```
Так же имеет значение json из которого формируется выборка, тот что доступен на серверах, годится только для официально поддерживаемых версий, модифицированный приложен в проект (php-releases.json), для 5.3, 5.4 в нём убрана информация про windows (из за фильтра jq).

TODO:
* Для 5.2 архивы исходников не подписаны, поэтому для него надо делать исключение
* Для наложения патчей, их набор, должен быть в каждом контексте (директории) сборки, автоматизировать синхронизацию, пока ручное копирование

# About this Repo

This is the Git repo of the Docker [official image](https://docs.docker.com/docker-hub/official_repos/) for [php](https://registry.hub.docker.com/_/php/). See [the Docker Hub page](https://registry.hub.docker.com/_/php/) for the full readme on how to use this Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/php](https://github.com/docker-library/docs/tree/master/php).

See a change merged here that doesn't show up on the Docker Hub yet? Check [the "library/php" manifest file in the docker-library/official-images repo](https://github.com/docker-library/official-images/blob/master/library/php), especially [PRs with the "library/php" label on that repo](https://github.com/docker-library/official-images/labels/library%2Fphp). For more information about the official images process, see the [docker-library/official-images readme](https://github.com/docker-library/official-images/blob/master/README.md).
