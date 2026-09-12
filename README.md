<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20&height=180&section=header&text=Yatube%20API&fontSize=70&fontAlignY=35&desc=REST%20API%20on%20Django%20%7C%20Yandex%20Practicum&descAlignY=55&descSize=18" alt="Banner" width="100%">

<img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Django-3.2.16-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
<img src="https://img.shields.io/badge/DRF-3.12.4-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django REST Framework">
<img src="https://img.shields.io/badge/SimpleJWT-4.7.2-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="SimpleJWT">
<img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">

<br>

<img src="https://img.shields.io/badge/Pytest-6.2.4-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="Pytest">
<img src="https://img.shields.io/badge/django--filter-2.4.0-092E20?style=for-the-badge&logo=django&logoColor=white" alt="django-filter">
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman">
<img src="https://img.shields.io/badge/Yandex-Practicum-red?style=for-the-badge&logo=yandex&logoColor=white" alt="Yandex Practicum">

<br><br>

<h2>🔌 Yatube API — финальная версия REST API</h2>

<p><b>Учебный проект в рамках курса «Python-разработчик» от Яндекс Практикума</b></p>

</div>

<hr>

<h2>📖 О проекте</h2>

<p><b>Yatube API</b> — финальная версия REST API для социальной сети блогов. Пользователи смогут публиковать посты, оставлять комментарии, подписываться на других авторов и объединять записи в сообщества. API строится на <b>Django REST Framework</b> с аутентификацией по <b>JWT-токенам</b>.</p>

<p>На текущем этапе реализованы <b>базовые модели</b>, подключено приложение <code>api</code>, подготовлены тесты и коллекция Postman. Реализация вьюх, сериализаторов и маршрутизации — в процессе.</p>

<hr>

<h2>✅ Что уже сделано</h2>

<ul>
  <li>Django-проект с приложениями <code>api</code> и <code>posts</code>.</li>
  <li>Модель <code>Post</code> — посты с полями <code>text</code>, <code>pub_date</code>, <code>author</code>, <code>image</code>.</li>
  <li>Модель <code>Comment</code> — комментарии с полями <code>author</code>, <code>post</code>, <code>text</code>, <code>created</code>.</li>
  <li>Подключён <code>rest_framework</code> и <code>rest_framework_simplejwt</code>.</li>
  <li>Настроены права по умолчанию: <code>IsAuthenticated</code> для всех эндпоинтов.</li>
  <li>Подготовлены тесты: JWT, посты, комментарии, группы, подписки.</li>
  <li>Готова коллекция Postman с инструкцией и bash-скриптом для подготовки данных.</li>
</ul>

<hr>

<h2>🚧 Что в разработке</h2>

<ul>
  <li>Модель <code>Group</code> — сообщества.</li>
  <li>Модель <code>Follow</code> — подписки на авторов.</li>
  <li>Сериализаторы для <code>Post</code>, <code>Comment</code>, <code>Group</code>, <code>Follow</code>.</li>
  <li>ViewSet'ы и маршрутизация API.</li>
  <li>JWT-аутентификация (эндпоинты <code>jwt/create/</code> и <code>jwt/refresh/</code>).</li>
  <li>Права доступа: редактирование и удаление только автором.</li>
  <li>Пагинация и фильтрация через <code>django-filter</code>.</li>
  <li>Настройка <code>MEDIA_URL</code> и <code>MEDIA_ROOT</code> для загрузки изображений.</li>
  <li>Настройка админки для моделей <code>Post</code> и <code>Comment</code>.</li>
</ul>

<hr>

<h2>🗃️ Модели данных</h2>

<div align="center">

<table>
  <thead>
    <tr>
      <th align="left">Модель</th>
      <th align="left">Поля</th>
      <th align="left">Статус</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Post</b></td>
      <td><code>text</code>, <code>pub_date</code>, <code>author</code>, <code>image</code></td>
      <td>✅</td>
    </tr>
    <tr>
      <td><b>Comment</b></td>
      <td><code>author</code>, <code>post</code>, <code>text</code>, <code>created</code></td>
      <td>✅</td>
    </tr>
    <tr>
      <td><b>Group</b></td>
      <td><code>title</code>, <code>slug</code>, <code>description</code></td>
      <td>🚧</td>
    </tr>
    <tr>
      <td><b>Follow</b></td>
      <td><code>user</code>, <code>following</code></td>
      <td>🚧</td>
    </tr>
  </tbody>
</table>

</div>

<hr>

<h2>⚙️ Настройки REST Framework</h2>

<p>В <code>settings.py</code> заданы права по умолчанию:</p>

<pre><code>REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
}</code></pre>

<p>То есть все эндпоинты по умолчанию доступны только авторизованным пользователям. JWT-аутентификация через <code>djangorestframework-simplejwt</code> пока не подключена.</p>

<hr>

<h2>🛠️ Технологии</h2>

<div align="center">

<table>
  <thead>
    <tr>
      <th align="left">Технология</th>
      <th align="left">Версия</th>
      <th align="left">Назначение</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b>Python</b></td><td>3.10+</td><td>Язык разработки</td></tr>
    <tr><td><b>Django</b></td><td>3.2.16</td><td>Веб-фреймворк</td></tr>
    <tr><td><b>Django REST Framework</b></td><td>3.12.4</td><td>Построение REST API</td></tr>
    <tr><td><b>djangorestframework-simplejwt</b></td><td>4.7.2</td><td>JWT-аутентификация</td></tr>
    <tr><td><b>django-filter</b></td><td>2.4.0</td><td>Фильтрация queryset'ов</td></tr>
    <tr><td><b>Pillow</b></td><td>9.3.0</td><td>Работа с изображениями</td></tr>
    <tr><td><b>PyJWT</b></td><td>2.1.0</td><td>Работа с JWT-токенами</td></tr>
    <tr><td><b>SQLite</b></td><td>—</td><td>База данных</td></tr>
    <tr><td><b>Pytest</b></td><td>6.2.4</td><td>Тестирование</td></tr>
    <tr><td><b>pytest-django</b></td><td>4.4.0</td><td>Интеграция pytest с Django</td></tr>
    <tr><td><b>requests</b></td><td>2.26.0</td><td>HTTP-запросы (для тестов)</td></tr>
    <tr><td><b>Postman</b></td><td>—</td><td>Ручное тестирование эндпоинтов</td></tr>
  </tbody>
</table>

</div>

<hr>

<h2>📂 Структура проекта</h2>

<pre><code>api-final-yatube-ad/
├── postman_collection/
│   ├── API_for_yatube.postman_collection.json  # Коллекция запросов
│   ├── README.md                               # Инструкция по запуску
│   └── set_up_data.sh                          # Скрипт для фикстур
├── tests/
│   ├── fixtures/
│   │   ├── __init__.py
│   │   ├── fixture_data.py      # Фикстуры данных (посты, комментарии)
│   │   └── fixture_user.py      # Фикстуры пользователей
│   ├── __init__.py
│   ├── conftest.py              # Общие настройки pytest
│   ├── test_comment.py          # Тесты комментариев
│   ├── test_follow.py           # Тесты подписок
│   ├── test_group.py            # Тесты сообществ
│   ├── test_jwt.py              # Тесты JWT-аутентификации
│   └── test_post.py             # Тесты постов
├── yatube_api/
│   ├── api/                     # Приложение API
│   ├── posts/
│   │   ├── migrations/          # Миграции БД
│   │   ├── __init__.py
│   │   ├── admin.py             # Админка (заготовка)
│   │   ├── apps.py              # Конфигурация приложения
│   │   ├── models.py            # Модели Post, Comment
│   │   ├── tests.py             # Тесты приложения
│   │   └── views.py             # Вьюхи (в разработке)
│   ├── yatube_api/              # Настройки проекта (settings, urls, wsgi)
│   └── manage.py                # Управляющий скрипт Django
├── README.md                    # Документация
├── pytest.ini                   # Конфигурация pytest
├── requirements.txt             # Зависимости проекта
└── setup.cfg                    # Конфигурация flake8</code></pre>

<hr>

<h2>🚀 Запуск</h2>

<h3>Требования</h3>
<ul>
  <li><b>Python</b> 3.10 или выше.</li>
  <li><b>pip</b> для установки зависимостей.</li>
  <li><b>Bash</b> для запуска скрипта подготовки данных.</li>
</ul>

<h3>Шаги</h3>
<ol>
  <li>
    <b>Клонируйте репозиторий:</b>
    <pre><code>git clone https://github.com/DarkSwordman999/api-final-yatube-ad.git
cd api-final-yatube-ad</code></pre>
  </li>
  <li>
    <b>Создайте и активируйте виртуальное окружение:</b>
    <pre><code>python -m venv venv

# Windows:
venv\Scripts\activate

# macOS / Linux:
source venv/bin/activate</code></pre>
  </li>
  <li>
    <b>Установите зависимости:</b>
    <pre><code>pip install -r requirements.txt</code></pre>
  </li>
  <li>
    <b>Подготовьте данные для Postman-коллекции:</b>
    <pre><code>cd postman_collection
bash set_up_data.sh</code></pre>
    <p><b>Внимание:</b> скрипт предварительно очищает базу данных.</p>
  </li>
  <li>
    <b>Запустите сервер разработки:</b>
    <pre><code>cd ../yatube_api
python manage.py runserver</code></pre>
  </li>
</ol>

<hr>

<h2>📬 Postman-коллекция</h2>

<p>В папке <code>postman_collection/</code> лежит файл <code>API_for_yatube.postman_collection.json</code> — набор заранее подготовленных запросов для проверки работы API. Подробная инструкция по импорту и запуску — в <a href="./postman_collection/README.md">README коллекции</a>.</p>

<p>Кратко:</p>
<ol>
  <li>Запустить <code>set_up_data.sh</code> для подготовки данных.</li>
  <li>Запустить тестовый сервер Django.</li>
  <li>Импортировать коллекцию в Postman (<code>File → Import</code>).</li>
  <li>Запустить коллекцию через <code>Run collection</code>.</li>
</ol>

<hr>

<h2>🧪 Тестирование</h2>

<p>Тесты запускаются через <b>pytest</b> с плагином <b>pytest-django</b>. Конфигурация — в <code>pytest.ini</code>.</p>

<pre><code>pytest</code></pre>

<p>Что проверяется:</p>
<ul>
  <li><b><code>test_jwt.py</code></b> — JWT-аутентификация.</li>
  <li><b><code>test_post.py</code></b> — посты.</li>
  <li><b><code>test_comment.py</code></b> — комментарии.</li>
  <li><b><code>test_group.py</code></b> — сообщества.</li>
  <li><b><code>test_follow.py</code></b> — подписки на авторов.</li>
</ul>

<p>Фикстуры:</p>
<ul>
  <li><b><code>fixtures/fixture_user.py</code></b> — тестовые пользователи.</li>
  <li><b><code>fixtures/fixture_data.py</code></b> — тестовые данные (посты, комментарии).</li>
</ul>

<p><b>Важно:</b> в <code>conftest.py</code> есть встроенная проверка — тесты не пройдут, если README остался в виде стандартной заглушки. Этот файл уже оформлен.</p>

<hr>

<h2>🧹 Линтинг</h2>

<p>Код проверяется линтером <b>flake8</b>. Настройки — в файле <code>setup.cfg</code>.</p>

<pre><code>flake8 .</code></pre>

<hr>

<h2>👤 Автор</h2>

<div align="center">

<p><b>DarkSwordman999</b></p>

<a href="https://github.com/DarkSwordman999">
  <img src="https://img.shields.io/badge/GitHub-DarkSwordman999-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

</div>

<hr>

<div align="center">

<h3>🎓 Проект создан в рамках курса «Python-разработчик» от <a href="https://practicum.yandex.ru/">Яндекс Практикума</a></h3>

<p><i>Учебный проект. Создан в образовательных целях.</i></p>

</div>
