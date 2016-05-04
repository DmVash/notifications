Middle PHP developer - тестовое задание
============================

Использую basic шаблон проекта Yii2 написать небольшое тестовой проект с авторизацией и ролями (админ и пользователь). 
В проекте на освное системы событий Yii разработать систему уведомлений, которая легко подключается к любым можелям


Структура приложения
--------------------

      assets/            
      commands/           
      config/             
      controllers/        
            /NotificationConttoler.php  контроллер для уведомлений
            /PostsContoller.php         контроллер статей
            /UserContoller.php          контроллер администрирований пользователей      
      models/             
            /NotificationHandler.php    реализует всю логику отправки уведомлений
            /Post.php                   модель для статей свзязанная с таблице post
            /SendingNotifiaction.php    модель для отправленых уведомлений которые записываются в таблицу sending_notification
            /SignupForm.php             модель формы регистрации
            /User.php                   модель свзянная с таблицей user
            /ViewedNotifications.php    модель реализующая просмотр уведомленийпользователями данные записываются в таблицу viewd_notification
            /Notifications.php           данная модель связана с таблицей notifications в которой хранятся шаблоны уведомлений
      runtime/            
      tests/              
      vendor/             
      views/             
      web/
            /site.js                    дополнительные js скрипты          



Описание
--------
В качестве RBAC manager используется PhpManager, при регистрации пользователь по умолчанию получает роль user, переназначить роль можной в файле `rbac/assignments.php`,
при логине пользователь попадает на страницу просмотра уведомлений.
Мной были реализованы все требования поставленные в задании, т.е на данные момент присутсвтуют два типа уведомлений email и browser с возможностью их дальнейшего расширения.
Админу доступна возможность создания своих уведомлений с выбором типа уведомления его кода, а также выбором адресата или отправки уведомления всем пользователям, 
также в расположении администратора имеется CRUD для статей, и функция управления пользователями с возможностью забанить пользователя, после чего он получит соответствующее сообщение на свою почту.


Конфигурация
------------

### База данных
Миграции находятся в папке `migration`, также на всякий случай я сделал дамп базы `rgk.sql`, который содержится там же
конфигурация подключения  бд:

```php
return [
    'class' => 'yii\db\Connection',
    'dsn' => 'mysql:host=localhost;dbname=rgk',
    'username' => 'root',
    'password' => '',
    'charset' => 'utf8',
];
```

Затраченное время
-----------------

С учетом ознакомления и освоения фреймворка на работу было затрачено приблизительно 35 часов
Ссылка на резюме https://docs.google.com/document/d/1D7RhC8QmlCySk-6kNTIO7P5ULfmF5h7gK6RSSgsVd30/edit?usp=sharing