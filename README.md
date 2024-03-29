### **Описание проекта:**

API-сервис для проекта Yatube - социальная сеть для публикации личных дневников, дает возможность создать учетную запись, публиковать записи, подписываться на любимых авторов и отмечать понравившиеся записи.


### **Используемые технологии:**

Python, 
Django, 
REST API


### **Автор проекта:**

Екатерина Мужжухина, e-mail: awesome-170693@yandex.ru, https://github.com/katekatekatem


### **Как запустить проект:**

Клонировать репозиторий и перейти в него в командной строке:

> git clone git@github.com:katekatekatem/api_final_yatube.git
> 
> cd api_final_yatube

Cоздать и активировать виртуальное окружение:

> python -m venv venv
> 
> source venv/scripts/activate

Установить зависимости из файла requirements.txt:

> python -m pip install --upgrade pip
> 
> pip install -r requirements.txt

Выполнить миграции:

> python manage.py migrate

Запустить проект:

> python manage.py runserver


### **Примеры запросов к API:**

POST .../api/v1/posts/

> {
> 
>     "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
>     
>     "group": 1
>     
> } 

Пример ответа:

> {
> 
>     "id": 14,
>     
>     "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
>     
>     "author": "anton",
>     
>     "image": null,
>     
>     "group": 1,
>     
>     "pub_date": "2021-06-01T08:47:11.084589Z"
>     
> } 

GET .../api/v1/groups/2/

Пример ответа:

> {
> 
>     "id": 2,
>     
>     "title": "Математика",
>     
>     "slug": "math",
>     
>     "description": "Посты на тему математики"
>     
> } 

POST .../api/v1/posts/14/comments/

> {
> 
>     "text": "тест тест"
>     
> } 

Пример ответа:

> {
> 
>     "id": 4,
>     
>     "author": "anton",
>     
>     "post": 14,
>     
>     "text": "тест тест",
>     
>     "created": "2021-06-01T10:14:51.388932Z"
>     
> } 