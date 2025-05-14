- [Об этом плейбуке](#об-этом-плейбуке)
- [Clickhouse, Vector, Lighthouse](#clickhouse-vector-lighthouse)
 - [Предварительные требования](#предварительные-требования)
 - [Конфигурация](#конфигурация)
 - [Установка](#установка)
- [Поддержка](#поддержка)
- [TODO](#todo)
- [Права](#права)

## Об этом Плейбуке

Коммьюнити версия плейбука для установки Clickhouse, Vector, Lighthouse

##  Clickhouse, Vector, Lighthouse

- Может быть использован как для установки на железо так и на ВМ. Докер контейнеры поддерживаются ограниченно в связи с отсутствием в дефолтной поставке нужного ПО.
- Устанавливает и конфигурирует сервисы Clickhouse, Vector и Lighthouse

### Предварительные требования

- **Ansible v2.16.3+**
- **Python 3.12.3+** 

### Конфигурация

- Для изменения дефолтных параметров смотрите файлы main.yaml в директориях `playbook/roles/clickhouse/defaults`, `playbook/roles/vector-role/defaults` и `playbook/roles/lighthouse-role/defaults`
- Конфигурация Вектора дополнительно может быть настроена через шаблоны `playbook/roles/vector/templates/vector.service.j2` и `playbook/roles/vector/templates/vector.toml.j2`
- Конфигурация lighthouse дополнительно может быть настроена через шаблоны `playbook/roles/lighthouse-role/templates/lighthouse.conf.j2`

### Установка

- Перед запуском плейбука перейдите в директорию `playbook`
- Установите зависимости через `ansible-galaxy install -r requirements.yaml`
- Cкорректируйте файл `playbook/inventory/prod.yaml` указав хосты и способы подключения.

```
#Запуск плейбука
ansible-playbook -i inventory/prod.yaml site.yml
```

## Поддержка

- Данный плейбук поставлется как-есть. Любое использование на ваш страх и риск.

## TODO

- В дальнейших планах развитие данного плейбука.

## Права

- Данный плейбук создан студентом Байковым Михаилом и предполагает свободное копирование и распространение.