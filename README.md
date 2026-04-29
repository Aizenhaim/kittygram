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

Если будет ошибка выполнения скриптов, выполните один раз:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
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

Запустить проект:

```powershell
python manage.py runserver
```

Сервер запустится на `http://localhost:8000`

---

#### Для Linux/Mac:

```bash
git clone https://github.com/Aizenhaim/kittygram.git
cd kittygram
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 manage.py migrate
python3 manage.py runserver
```
