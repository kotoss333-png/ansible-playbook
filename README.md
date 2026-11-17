# Домашнее задание к занятию 4 «Работа с roles»

## Описание

Playbook разворачивает стек из трёх компонентов с использованием отдельных Ansible-ролей:
- **ClickHouse** — устанавливается из внешней роли `AlexeySetevoi/ansible-clickhouse` (версия `1.13`).
- **Vector** — устанавливается и настраивается с помощью собственной роли `vector-role` (версия `1.0.0`).
- **LightHouse** — веб-интерфейс для ClickHouse разворачивается под управлением Nginx с помощью собственной роли `lighthouse-role` (версия `1.0.0`).

## Подготовка и запуск

1. Установить все необходимые роли из `requirements.yml`:
   ```bash
   ansible-galaxy install -r requirements.yml -p roles
   ```
2. Указать актуальные IP-адреса хостов в файле `inventory/prod.yml`.
3. Запустить playbook:
   ```bash
   ansible-playbook -i inventory/prod.yml site.yml
   ```

## Ссылки на репозитории

- **Репозиторий с ролью Vector:** https://github.com/kotoss333-png/vector-role
- **Репозиторий с ролью LightHouse:** https://github.com/kotoss333-png/lighthouse-role
- **Репозиторий с Playbook:** https://github.com/kotoss333-png/ansible-playbook
