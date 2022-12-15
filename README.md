# DjangoCheatlist

https://ru.wikipedia.org/wiki/Django

https://www.jetbrains.com/ru-ru/pycharm/

https://www.python.org/

https://www.djangoproject.com/

https://djbook.ru/

https://django.fun/

https://conemu.github.io/


Установка виртуального окружения
====================================
# Windows
python -m venv venv

# Linux
python3 -m venv venv

Активация виртуального окружения
====================================
# Windows
.\venv\Scripts\activate

# Linux
source venv/bin/activate


pip install Django

django-admin startproject mysite

python manage.py runserver
python manage.py runserver 4000
python manage.py runserver 1.2.3.4:4000

python manage.py startapp news

pip install Pillow

python manage.py makemigrations

python manage.py sqlmigrate news 0001

python manage.py migrate

python manage.py shell

from news.models import News

from django.db import connection
connection.queries

news1 = News(title='Новость 1', content='Контент новости 1')
news1.save()
news1.pk


news2 = News()
news2.title = 'Новость 2'
news2.content = 'Контент новости 2'
news2.save()


news3 = News.objects.create(title='Новость 3', content='Контент новости 3')
news3.pk


def __str__(self):
    return self.title


news = News.objects.all()
for item in news:
	print(item.title, item.is_published)


News.objects.filter(title='News 5')


News.objects.get(pk=3)


UPDATE
news7 = News.objects.get(pk=7)
news7.title = 'News 6'
news7.save()


DELETE
news7.delete()


ORDER BY
News.objects.order_by('title')
News.objects.order_by('-title')


News.objects.exclude(title='Lorem ipsum')




