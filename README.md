# JMeter-TestAPI

ЗАДАНИЕ:
Используя Public API https://reqres.in проверьте (с помощью JMeter):
● получение списка пользователей
● регистрацию и авторизацию

РЕШЕНИЕ в src/test/jmeter/jmeter-testapi.jmx.

● Настройки HTTP Request Defaults:
 - протокол = https
 - имя сервера = reqres.in

● Thread Group 1 - 'List Users (GET)'
 - получает список пользователей по строке GET-запроса "https://reqres.in/api/users?page=2"
 - JSON Extractor выбирает значения first_name и last_name из полученных данных
 - проверяется ожидаемый код ответа успешного запроса (200)
 - проверяется наличие имени из списка

● Thread Group 2 - 'Register (POST)'
- проверяет успешную и неуспешную регистрацию отправляя регистрационные данные в теле POST-запроса в формате JSON 
- для успешного случая проверяется значение ожидаемого токена
- для неуспешного случая проверяется значение ожидаемого кода ответа (400)

● Thread Group 3 - 'Login (POST)'
- проверяет успешный и неуспешный логин отправляя регистрационные данные в теле POST-запроса в формате JSON 
- для успешного и неуспешного случаев проверяется значение ожидаемого токена
