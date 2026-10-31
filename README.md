# Лабораторная работа № 4 — Страницы статей

Созданы архив статей и отдельные страницы с переходами между ними. Вариант № 30 — «Сдача в аренду торговых площадей».

## Запуск

Установите Python 3.11 и выполните в PowerShell из папки проекта:

Для сохранения входа при перезапуске используйте один и тот же ключ Django.

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
$env:DJANGO_SECRET_KEY = Read-Host "Ключ Django"
.\.venv\Scripts\python.exe src/manage.py migrate
.\.venv\Scripts\python.exe src/manage.py loaddata demo
.\.venv\Scripts\python.exe src/manage.py createsuperuser
.\.venv\Scripts\python.exe src/manage.py runserver
```

Откройте http://127.0.0.1:8000/. Административная панель: http://127.0.0.1:8000/admin/. Команда `loaddata demo` добавляет учебные данные; статьи можно создать через административную панель.
