# Добавлено ДЗ по семинару 7
## Домашнее задание
1. При помощи регулярных выражений усильте проверку данных в validateRequestData так, чтобы пользователь не смог передать на обработку любую строку, содержащую HTML-теги
2. Доработайте шаблон аутентификации. В нем нужно добавить две вещи:
    В приветствии нужно выводить имя залогинившегося пользователя.
    Также надо выводить ссылку «Выйти из системы», которая будет уничтожать сессию пользователя.
3. Переработайте имеющийся функционал приложения на формы.
    Создание, обновление и удаление пользователя теперь должно производиться через формы.
    Если пользователь обновляется, в форму должны быть выведены текущие значения. Это может быть сделано ссылкой из списка пользователей (рядом с каждым из них будет своя ссылка “Обновить данные”).
4. *Создайте функцию “Запомнить меня” в форме логина.
    В форме должен появиться checkbox “Запомнить меня”.
    При нажатии на него в процессе логина пользователю выдаётся cookie, по которому происходит автоматическая авторизация, даже если сессия закончилась.
    При логине нужно будет генерировать токен из random_bytes(), размещая его в cookies и БД, чтобы сравнивать их
    При выходе из системы токен надо деактивировать.
5. Исправьте потолстевший Абстрактный контроллер.

# Добавлено ДЗ по семинару 6
## Домашнее задание
1. Мы стали работать с исключениями. Создайте в Render логику обработки исключений так, чтобы она встраивалась в общий шаблон. Вызов будет выглядеть примерно так:
    ```
    try{
        $app = new Application();
        echo $app->run();
    }
        catch(Exception $e){
        echo Render::renderExceptionPage($e);`
    }
    ```
2. Создайте метод обновления пользователя новыми данными. Например,
    >/user/update/?id=42&name=Петр
    Такой вызов обновит имя у пользователя с ID 42. Обратите внимание, что остальные поля не меняются. Также помните, что пользователя с ID 42 может и не быть в базе.
3. Создайте метод удаления пользователя из базы. Учитывайте, что пользователя может не быть в базе
    >/user/delete/?id=42
<br/>
<hr>    


# Добавлено ДЗ по семинару 5

## Домашнее задание

1. Добавьте к шаблону подключение файлов стилей так, чтобы в дальнейшем можно было дорабатывать внешний вид системы.

2. Сформируйте еще три подключаемых к скелету блока – шапку сайта (она всегда будет одинаковой по стилю и располагаться в самой верхней части), подвал сайта (также одинаковый, но в нижней части) и sidebar (боковая колонка, которую можно наполнять новыми элементами).

3. Средствами TWIG выводите на экран текущее время.

4. Создайте обработку страницы ошибки. Например, если контроллер на найден, то нужно вызывать специальный метод рендеринга, который сформирует специальную страницу ошибок.

5. Для страницы ошибок формируйте HTTP-ответ 404. Это можно сделать при помощи функции header.

6. Реализуйте функционал сохранения пользователя в хранилище. Сохранение будет происходить при помощи GET-запроса.

   > /user/save/?name=Иван&birthday=05-05-1991