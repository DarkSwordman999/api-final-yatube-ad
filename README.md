<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20&height=180&section=header&text=Yatube%20API&fontSize=70&fontAlignY=35&desc=REST%20API%20on%20Django%20%7C%20Yandex%20Practicum&descAlignY=55&descSize=18" alt="Banner" width="100%">

<br>

<img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Django-3.2.16-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
<img src="https://img.shields.io/badge/DRF-3.12.4-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django REST Framework">
<img src="https://img.shields.io/badge/SimpleJWT-4.7.2-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="SimpleJWT">
<img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">

<br><br>

<img src="https://img.shields.io/badge/Pytest-6.2.4-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="Pytest">
<img src="https://img.shields.io/badge/django--filter-2.4.0-092E20?style=for-the-badge&logo=django&logoColor=white" alt="django-filter">
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman">
<img src="https://img.shields.io/badge/Yandex-Practicum-red?style=for-the-badge&logo=yandex&logoColor=white" alt="Yandex Practicum">

<br><br>

<h2>🔌 Yatube API — REST API для социальной сети</h2>

<p><b>Учебный проект в рамках курса «Python-разработчик» от Яндекс Практикума</b></p>

</div>

---

## 📖 О проекте

**Yatube API** — REST API для социальной сети блогов, построенный на **Django REST Framework**.

Проект предоставляет основу для работы с публикациями, комментариями, сообществами и подписками на авторов. Для аутентификации предусмотрено использование **JWT-токенов**.

На текущем этапе реализована базовая структура проекта: модели публикаций и комментариев, приложение API, настройки REST Framework, тестовая инфраструктура и коллекция запросов для Postman.

Часть функциональности находится в разработке: сериализаторы, ViewSet'ы, маршрутизация, JWT-эндпоинты, права доступа, пагинация, фильтрация и работа с изображениями.

---

## ✨ Возможности проекта

### ✅ Уже реализовано

* Django-проект с приложениями `api` и `posts`.
* Модель `Post`.
* Модель `Comment`.
* Подключение Django REST Framework.
* Подключение `djangorestframework-simplejwt`.
* Базовые настройки прав доступа.
* Тестовая инфраструктура на `pytest`.
* Фикстуры пользователей и тестовых данных.
* Тесты для постов, комментариев, групп, подписок и JWT.
* Postman-коллекция для проверки API.
* Bash-скрипт для подготовки тестовых данных.

### 🚧 В разработке

* Модель `Group` для сообществ.
* Модель `Follow` для подписок.
* Сериализаторы для всех API-моделей.
* ViewSet'ы и маршрутизация.
* JWT-эндпоинты:

  * `jwt/create/`
  * `jwt/refresh/`
* Разграничение прав доступа.
* Редактирование и удаление объектов только их авторами.
* Пагинация.
* Фильтрация через `django-filter`.
* Работа с загружаемыми изображениями.
* Настройка `MEDIA_URL` и `MEDIA_ROOT`.
* Расширение административной панели.

---

## 🗃️ Модели данных

| Модель      | Основные поля                         | Статус |
| ----------- | ------------------------------------- | :----: |
| **Post**    | `text`, `pub_date`, `author`, `image` |    ✅   |
| **Comment** | `author`, `post`, `text`, `created`   |    ✅   |
| **Group**   | `title`, `slug`, `description`        |   🚧   |
| **Follow**  | `user`, `following`                   |   🚧   |

### 📝 Post

Модель публикации содержит:

* текст поста;
* дату публикации;
* автора;
* изображение.

### 💬 Comment

Комментарий связан с конкретным постом и содержит:

* автора;
* пост;
* текст комментария;
* дату создания.

### 👥 Group

Будущая модель сообщества с названием, уникальным `slug` и описанием.

### 🔔 Follow

Будущая модель подписки одного пользователя на другого.

---

## ⚙️ Настройки REST Framework

В проекте настроены права доступа по умолчанию:

```python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
}
```

Таким образом, эндпоинты API по умолчанию доступны только авторизованным пользователям.

> **Важно:** несмотря на наличие `djangorestframework-simplejwt` среди зависимостей проекта, подключение JWT-аутентификации и соответствующих эндпоинтов находится в разработке.

---

## 🧪 Тестовая инфраструктура

Для тестирования используется связка:

* **Pytest**
* **pytest-django**
* Django Test Framework
* собственные фикстуры проекта

Тесты разделены по функциональным областям:

| Файл              | Назначение             |
| ----------------- | ---------------------- |
| `test_post.py`    | Работа с постами       |
| `test_comment.py` | Работа с комментариями |
| `test_group.py`   | Работа с сообществами  |
| `test_follow.py`  | Подписки на авторов    |
| `test_jwt.py`     | JWT-аутентификация     |

Фикстуры находятся в каталоге `tests/fixtures/`:

* `fixture_user.py` — тестовые пользователи;
* `fixture_data.py` — тестовые данные.

Общие настройки pytest находятся в `tests/conftest.py`.

---

## 📬 Postman

В каталоге `postman_collection/` находится готовая коллекция запросов для ручного тестирования API.

```text
postman_collection/
├── API_for_yatube.postman_collection.json
├── README.md
└── set_up_data.sh
```

### Быстрый сценарий

1. Подготовить тестовые данные.
2. Запустить Django-сервер.
3. Импортировать коллекцию в Postman.
4. Запустить коллекцию через `Run collection`.

> ⚠️ Скрипт `set_up_data.sh` предварительно очищает базу данных, поэтому не запускайте его на базе с важными данными.

---

## 📂 Структура проекта

```text
api-final-yatube-ad/
├── postman_collection/
│   ├── API_for_yatube.postman_collection.json
│   ├── README.md
│   └── set_up_data.sh
│
├── tests/
│   ├── fixtures/
│   │   ├── __init__.py
│   │   ├── fixture_data.py
│   │   └── fixture_user.py
│   ├── __init__.py
│   ├── conftest.py
│   ├── test_comment.py
│   ├── test_follow.py
│   ├── test_group.py
│   ├── test_jwt.py
│   └── test_post.py
│
├── yatube_api/
│   ├── api/
│   ├── posts/
│   │   ├── migrations/
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── models.py
│   │   ├── tests.py
│   │   └── views.py
│   ├── yatube_api/
│   └── manage.py
│
├── .gitignore
├── README.md
├── pytest.ini
├── requirements.txt
└── setup.cfg
```

---

## 🛠️ Технологический стек

| Технология                        | Версия | Назначение                 |
| --------------------------------- | -----: | -------------------------- |
| **Python**                        |  3.10+ | Язык разработки            |
| **Django**                        | 3.2.16 | Веб-фреймворк              |
| **Django REST Framework**         | 3.12.4 | Создание REST API          |
| **djangorestframework-simplejwt** |  4.7.2 | JWT-аутентификация         |
| **django-filter**                 |  2.4.0 | Фильтрация queryset'ов     |
| **Pillow**                        |  9.3.0 | Работа с изображениями     |
| **PyJWT**                         |  2.1.0 | Работа с JWT               |
| **SQLite**                        |      — | База данных                |
| **Pytest**                        |  6.2.4 | Тестирование               |
| **pytest-django**                 |  4.4.0 | Интеграция Pytest с Django |
| **requests**                      | 2.26.0 | HTTP-запросы в тестах      |
| **Postman**                       |      — | Ручное тестирование API    |

---

## 🚀 Установка и запуск

### Требования

* Python **3.10+**
* `pip`
* Bash — для запуска `set_up_data.sh`

<details>
<summary><b>1. Клонирование репозитория</b></summary>

```bash
git clone https://github.com/DarkSwordman999/api-final-yatube-ad.git
cd api-final-yatube-ad
```

</details>

<details>
<summary><b>2. Создание виртуального окружения</b></summary>

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

</details>

<details>
<summary><b>3. Установка зависимостей</b></summary>

```bash
pip install -r requirements.txt
```

</details>

<details>
<summary><b>4. Подготовка данных</b></summary>

Перейдите в каталог Postman и запустите скрипт:

```bash
cd postman_collection
bash set_up_data.sh
```

> ⚠️ Скрипт очищает базу данных перед подготовкой тестовых данных.

</details>

<details>
<summary><b>5. Запуск Django</b></summary>

```bash
cd ../yatube_api
python manage.py runserver
```

После запуска проект будет доступен по адресу:

```text
http://127.0.0.1:8000/
```

</details>

---

## 🧪 Запуск тестов

Для запуска полного набора тестов:

```bash
pytest
```

Для подробного вывода:

```bash
pytest -v
```

Конфигурация находится в `pytest.ini`:

```ini
python_paths = yatube_api/
DJANGO_SETTINGS_MODULE = yatube_api.settings
testpaths = tests/
addopts = -vv -p no:cacheprovider
```

---

## 🧹 Линтинг

Для проверки качества кода используется **flake8**.

Запуск:

```bash
flake8 .
```

Основные настройки находятся в `setup.cfg`.

В конфигурации учитываются:

* максимальная цикломатическая сложность — `10`;
* исключение `tests/`;
* исключение директорий миграций;
* исключение виртуальных окружений;
* дополнительные правила проекта.

---

## 📄 Лицензия

Проект создан в образовательных целях в рамках курса **«Python-разработчик» от Яндекс Практикума**.

---

## 👤 Автор

<div align="center">

<b>DarkSwordman999</b>

<br><br>

<a href="https://github.com/DarkSwordman999">
  <img src="https://img.shields.io/badge/GitHub-DarkSwordman999-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

</div>

---

<div align="center">

### ⭐ Понравился проект?

Если **Yatube API** оказался полезным или интересным,
**поставьте ⭐ репозиторию на GitHub** — это лучшая поддержка проекта!

<br>

<a href="https://github.com/DarkSwordman999/api-final-yatube-ad">
  <img src="https://img.shields.io/badge/⭐%20Star%20repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="Star repository">
</a>

<br><br>

<i>Спасибо за интерес к проекту! 🚀</i>

</div>

---

<div align="center">

### 🎓 Яндекс Практикум

<i>Учебный проект, созданный в рамках курса «Python-разработчик».</i>

</div>
