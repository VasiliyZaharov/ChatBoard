# [JavaScript + Django Project ChatBoard](http://127.0.0.1:8000/accounts/login/)
## [Skillfactory](https://skillfactory.ru) FPW Homework

Пример веб-приложения, демонстрирующий взаимодействие интерфейса JavaScript и серверной части Django framework
<hr>
<p> </p>

:arrow_down: [перейти к старту проекта](README.md#Старт-проекта)

<p> </p>

## Техническое задание и реализация  
<br>
Нам необходимо создать базовый мессенжер со следующими функциями:
<br>
- отправка и получение сообщений;

*Отправка и получение сообщений реализованы через [Channels Django](https://channels.readthedocs.io/en/stable/introduction.html) , которые устанавливают длительное соединение с пользователем по протоколу WebSockets.*

<br>
- создание, редактирование и удаление групповых чатов и переписка в них;

*Пользователь открывает свою комнату (Room) или присоединяется к действующим комнатам, которые основываются на технологии объединения Django Channels в группы Groups для обмена сообщениями между разными каналами.*

*Пользователи подключаются и выходят из комнат динамически, вход и выход обозначаются сообщением от пользователя.*

*Сообщения отправляются всем пользователям в комнате.*

*Сохранение сообщений для пользователей, покинувших комнату, не предусмотрено. При выходе всех пользователей из комнаты она становится недоступной.*

<br>
- редактирование личной информации пользователя (имя и аватар);

*Зарегистрированным пользователям доступна страница Профиль с возможностью добавления/редактирования имени, емейла, короткого текста о себе и аватара.*

<br>
- просмотр списка других пользователей с переходом на отправку им сообщений.

*Находясь в комнате чата пользователь видит динамический список других пользователей, подключенных к этой же комнате.*

*При выборе конкретного пользователя открывается форма для отправки личных сообщений. У получателя сообщения отображаются в общем чате с пометкой, что они персональные.*

<br>

### Старт проекта

Опции и библиотеки, зависящие от платформы, адаптированы к Windows.

Клонирование хранилища в каталог ChatBoard
```bash
git clone https://github.com/VasiliyZaharov/ChatBoard
```
После загрузки проваливаемся в проект
```bash
cd ChatBoard/prjchat
```

Генерируем секретный ключ Django
```bash
python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
```

Во внутреннем каталоге prjchat (каталог проекта) добавьте файл venv/settings.env для частных настроек 
```python
SECRET_KEY = ''
```  

В каталоге ChatBoard запустите и настройте виртуальную среду
```bash
python -m venv venvCB
```
```bash
venvCB\scripts\activate
```
```bash
pip install -r requirements.txt
```

Создаем суперпользователя
```
python manage.py createsuperuser
``` 

Запускаем сервер
```bash
python manage.py runserver
```

Главная страница работает по адресу http://127.0.0.1:8000/ - локальный хост, о котором сервер сообщает вам в стартовом сообщении

[ChatBoard](http://127.0.0.1:8000/)
<p> </p>
<p> </p>

:arrow_up: [К самому началу](README.md#Техническое-задание-и-реализация)

<br><br>
