### Как запустить проект:

#### Для Windows (PowerShell):

Клонировать репозиторий и перейти в него:

```powershell
git clone https://github.com/Aizenhaim/kittygram.git
cd kittygram
```

Создать и активировать виртуальное окружение:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

Обновить pip и установить зависимости:

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Выполнить миграции:

```powershell
python manage.py migrate
```

Создать суперпользователя для админки:

```powershell
python manage.py createsuperuser
```

Введите:
- Username: `admin`
- Email: `admin@example.com`
- Password: `admin123`

Запустить проект:

```powershell
python manage.py runserver
```

Сервер запустится на `http://localhost:8000`

#### Доступ к приложению

**Админка (для тестирования):**
```
http://localhost:8000/admin/
Логин: admin
Пароль: admin123
```

**API документация (Swagger):**
```
http://localhost:8000/swagger/
(доступна после входа в админку)
```

**API документация (ReDoc):**
```
http://localhost:8000/redoc/
```

**API основной эндпоинт:**
```
http://localhost:8000/api/
```

---

#### Для Linux/Mac:

```bash
git clone https://github.com/Aizenhaim/kittygram.git
cd kittygram
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 manage.py migrate
python3 manage.py createsuperuser
python3 manage.py runserver
```

---

## Запуск через Docker

### Требования
- Docker установлен: `docker --version`
- Docker Compose установлен: `docker-compose --version`

### Запуск контейнеров

```powershell
# Запустить контейнеры в фоне
docker-compose up -d

# Просмотр логов
docker-compose logs -f web

# Проверить статус контейнеров
docker-compose ps
```

Приложение будет доступно на `http://localhost:8000`

### Остановка контейнеров

```powershell
# Остановить контейнеры (данные сохранятся)
docker-compose stop

# Остановить и удалить контейнеры
docker-compose down

# Полная очистка (удалить контейнеры, volumes, images)
docker-compose down -v
```

### Другие полезные команды

```powershell
# Пересоздать контейнеры (если изменился код)
docker-compose up -d --build

# Выполнить команду в контейнере
docker-compose exec web python manage.py migrate

# Создать суперпользователя в контейнере
docker-compose exec web python manage.py createsuperuser

# Просмотр списка контейнеров
docker ps

# Просмотр всех images
docker images
```
