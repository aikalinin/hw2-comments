### Понятный интерфейс (-0.1)

- не понятно, где какой заказ
    ```
    Order was successfully created
    
    
    1. Create order,
    2. Add dish into the order,
    3. Pay order,
    4. Cancel order
    5. Give review
    6. Exit
    3
    Your ready for payment orders:
    412ab431-83c6-4a36-b5a2-9d38e597f152
    a65f1c3a-049c-4c06-908f-2a1abb31b776
    Enter id of order to pay it: 
    ```

### CodeStyle

- Scheduler класс нигде не используется

### Общее (-0.6)

- Нет в приложении *Система должна отображать актуальный статус заказа (например, "принят","
  готовится", "готов")*, но в файлах есть **(-0.1)**
- Нет *Система приоритетов для обработки заказов* **(-0.5)**

### Ошибки (-1)

- Поскольку нет возможности менять пути к файлам, то может возникнуть ошибка доступа к файлу,
  которую никак не починить без пересборки (-1)
  ![Gakal_Angelica_FileNotFound.png](img%2FGakal_Angelica_FileNotFound.png)

### Итог: 8.3