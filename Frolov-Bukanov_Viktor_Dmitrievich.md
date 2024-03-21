### Применение принципов ООП и SOLID (-0.2)

- Для кухни сервисный слой выделен, а для админа, посетителя и пользователя почему-то нет, хотя
  контроллер как минимум берёт на себя две ответственности (речь про SRP) обработку запроса и бизнес
  логика

### Использование шаблонов проектирования (-1)

- просто нет, в коде не нашёл, в readme ничего не упомянуто

### Аутентификация (-0.1)

- передача объекта пользователя в другой контроллер очень слишком, в рамках этой дз не снижается
  оценка, но такой подход не используется
- пароли в чистом виде не передают (обсуждали на семинарах и в дз1)

### Понятный интерфейс (-0.1)
- в API нет методов для получения id блюд, то есть для вызова *createOrder* мне нужно лезть в БД

### Общее

- нет системы приоритетов (-0.5)
- для *Посетители могут составлять заказ, выбирая блюда из актуального меню.* нет самого меню (-0.3)
- нет *Система должна отображать актуальный статус заказа* (-0.3)
- entityManager.createNativeQuery использовать не имеет смысла, если вы используете репозитории, они
  могут ровно то же самое и вам даже sql запрос писать не нужно. Пример
  для `SELECT * FROM menu WHERE name = '$name' AND description = '$description' AND price = '$price' AND minutes_to_cook = '$minutesToCook'` ->
  в UserRepository будет
  ```java 
  fun findByUsernameAndPasswordAndType(username: String, password: String, type: String): User
  ```
  реализацию spring сам сделает

### Ошибки

- 500 ошибка если нет заказов в системе на запрос getRevenue (-0.5)
  ```java 
    java.lang.NullPointerException: null cannot be cast to non-null type java.math.BigDecimal 
    at ru.hse.restaurant.controllers.AdminControllerImpl.getRevenue(AdminController.kt:111) ~[main/:na]
  ```
- 500 ошибка для получения средней оценки (-0.5)
  ```java
  java.lang.NullPointerException: null cannot be cast to non-null type java.math.BigDecimal
  	at ru.hse.restaurant.controllers.AdminControllerImpl.getAverageAssessment(AdminController.kt:141) ~[main/:na]
  ```

### Итог: 6.5
