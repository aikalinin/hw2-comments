### Применение принципов ООП и SOLID (-0.4)

- с точки зрения классов декомпозировано хорошо, хотя не хватает сервисного слоя, чтобы объединить
  все взаимодействия в одном месте. Но внутри у бизнес-классов очень большие методы, которые ну точно можно было раскидать на внутренние методы
- SQL запросы ну можно было вынести в какой-нибудь класс и там собирать относительно нужд. Как раз тут и SRP проявляется, что будет отдельно ответственный класс за взаимодействие с БД

### CodeStyle (-0.3)
 - неиспользуемые импорты
 - в Котлине явно в теле класса описывать поля не нужно,
  можно переделать из такого:
  ```kotlin 
    class Order(dishes: String, price: Int, time: Int, userName: String, status: String): Entity() { 
      private var dishes: String
      private var price: Int
      private var time: Int
      private var status: String
      private var userName: String
        
      // ...
    }
  ```
  в
  ```kotlin 
     class Order(
       private var dishes: String,
       private var price: Int,
       private var time: Int,
       private var userName: String,
       private var status: String
     ) : Entity() {
        
        // ...
    }
  ```
 - в интерфейсе CRUD не нужно добавлять `{}`, это интерфейс, методы будут объявлены у наследников. При этом CRUD интерфейсе смысла нет, можно было методы оставить у `EntityTable`

### Общее 

- нет системы приоритетов **(-0.5)**

### Итог: 8.8