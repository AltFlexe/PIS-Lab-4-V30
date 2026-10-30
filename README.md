# Лабораторная работа 4 — страницы статей Django

Проект продолжает учебное приложение об аренде торговых помещений. Архив показывает статьи, а название каждой статьи ведёт на отдельную страницу с полным текстом. Если записи нет, возвращается ошибка 404. В административной панели доступны статьи и модели аренды.

## Запуск

При установленном Python 3.11 из корня проекта в PowerShell:

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe src/manage.py migrate
.\.venv\Scripts\python.exe src/manage.py loaddata demo
.\.venv\Scripts\python.exe src/manage.py createsuperuser
.\.venv\Scripts\python.exe src/manage.py test articles
.\.venv\Scripts\python.exe src/manage.py runserver
```

Главная страница доступна по адресу `http://127.0.0.1:8000/`, панель администратора — `/admin/`. В новой базе необходимо создать статьи через панель. Команда `loaddata demo` добавляет учебные помещения, арендатора, договор, периоды и платёж. Ключ Django берётся из `DJANGO_SECRET_KEY` или создаётся случайно для локального запуска.

Шаблоны, стили и представления находятся в `src/articles/`. Сроки аренды одного помещения не должны пересекаться; границы периодов включительны. Дополнительная проверка на уровне базы предназначена для SQLite.
