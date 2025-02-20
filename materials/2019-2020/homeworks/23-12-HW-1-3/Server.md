# Да се напише програма за сървър, който обработва заявки.

Заявката съдържа IP адрес на подателя и път към ресурса, който се иска. Някои заявки съдържат и допълнителни аргументи.
Отговорът на заявка съдържа статус (пр. 200, 404) и текст.
Сървърът съдържа списък от пътищата, които може да обработва, и съответни обекти, които ги обработват и връщат отговор. Има метод `Response* routeRequest(Request* req)`, който обработва заявката.
Всеки обект за обработка на заявка има един единствен метод `Response* handleRequest(Request* req)`, който обработва заявката и връща съответния отговор.
Добавете константен глобално достъпен списък от потребители с име и парола.

Пример за заявки и техните отговори:
 /login.html - връща текста `<html>login</html>` и статус 200
 /home.html - връща текста `<html>home</html>` и статус 200
 /api/login - като допълнителни аргументи получава име и парола. Връща текста `OK` и статус 200 ако този потребител съществува или текста `Unauthorized` и статус 403 ако този потребител не съществува.
 /api/get_users - връща като текст имената на всички потребители във формата `["user1", "user2", ... "userN"]`